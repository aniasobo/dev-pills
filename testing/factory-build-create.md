# Factories: `create` vs `build`

`create` persists the instance of the model; less performant because writes to db; good for testing things with callbacks on creation; will call the Active Record validations.

`build` only keeps the instance in memory; does not call `save!` so the Active Record validations won't run; no db access required.


```
before(:each) do
  @user = Factory.build(:user)  # returns an unsaved object
  @user = Factory.create(:user) # returns a saved object
  @user = Factory(:user)        # shortcut for Factory.create()
end
```

