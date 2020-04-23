# Factory Girl / Factory Bot

## Example use:

```
let!(:flags) do
  2.times { create(:flag, :approved, worker: worker) }
end
```

The `:approved` argument is a method defined in `factories/flags.rb`:

```
trait :approved do
  status { :approved }
  approved_by { create(:super_admin).id }
end
```

UNLESS FACTORY IS MEANT TO BE REUSED - use an existing basic factory and amend its details in the test itself, like this:

Existing `region` factory within the `user` factory:

```
factory :user, class: User do
  first_name { 'Joe' }
  last_name  { 'Blogs' }
  password   { 'password' }
  post_code { 'NW1 7AH' }
  region { create :region }
end
```

Manipulated in a spec file to add postcodes array:

```
def and_they_live_in_a_valid_region
  region = create :region, post_codes: ['N4']        # passes the array of postcodes to the factory
end
```

---

## Structuring and refactoring your suite

Start with creating local variables.

Refactor them into `let`s if you end up using them multiple times within the same block.

```
context 'thing' do
  let!(:shift) { create(:shift) }       ### this is the refactor

  it 'first test' do
    shift = create(:shift)              ### local vars for first test
    worker = create(:compliant_nurse)
  end

  it 'second test' do
    shift = create(:shift)              ### oh I need this var again, better refactor into let on context level!
end
```

---

## Resources:

- good [FactoryBot cheatsheet](https://devhints.io/factory_bot)
