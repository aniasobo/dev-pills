# Writing better ActiveRecord models

Source: Relearning ActiveRecord & Dealing with fat models in _Growing Rails Applications in Practice_ by Henning Koch & Thomas Eisenbarth

## Responsibilities of a model:

1. validation of data entered by user - uniqueness of username, password format etc
2. form roundtrip - revalidation
3. lifecycle callbacks

- express those in _validations and callbacks_ instead of Ruby methods
- use ActiveRecord's error tracking instead of keeping errors in variables
- when manipulating a record, put it in a "dirty" state - then inspect it and preview the changes before committing it; once the record passes validations, commit all changes to the db _in a single transaction_

## Plain model:

```
class PlainModel

  include ActiveModel::Model
  include ActiveSupport::Callbacks
  include ActiveModel::Validations::Callbacks

  define_callbacks :save

  def save
    if valid?
      run_callbacks :save do
        true
      end
    else
      false
    end
  end
end
```

**Sample implementation of the above in a sign-in form:**

```
class SignIn < ActiveType::Object

  attribute :email, :string
  attribute :password, :string

  validate :validate_user_exists
  validate :validate_password_correct

  def user
    User.find_by_email(email) if email.present?
  end

  private

  def validate_user_exists
    if user.blank?
      errors.add(:user_id, 'User not found')
    end
  end

  def validate_password_correct
    if user && !user.has_password?(password)
      errors.add(:password, 'Incorrect password')
    end
  end

end
```

## Fat models

### Characteristics of a fat model:

- too many callbacks that might get triggered at the wrong points in the app (for example, a background job that syncs data might trigger an `after_save` action on a user account and spam them)
- too many configuration flags that enable and disable actions based on the view
- increasingly hard unit tests because of the requirement to stub out countless side effects

### Refactoring fat models:

- abstract out classes like `PasswordRecovery`, `RegistrationForm` etc
- reduce the model into a slim _core model_
- core model should only contain:
  - a minimum set of validations to enforce data integrity
  - definitions of associations
  - universally useful convenience methods to find or manipulate records
- core model should **NOT** contain:
  - validations that only happen on a particular form
  - virtual attributes to support forms that do not map 1:1 to your database tables
  - callbacks that should only fire for a particular screen or use case
  - code to support authorization
  - helper methods to facilitate rendering of complex views
- the above should live in a _form model_ which only facilitates a single UI interaction
