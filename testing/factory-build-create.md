# Factories: `create` vs `build`

`create` persists the instance of the model; less performant because writes to db; good for testing things with callbacks on creation; will call the Active Record validations.

`build` is the equivalent of `Class.new` - it only keeps the instance in memory; does not call `save!` so the Active Record validations won't run; no db access required. To test after create callbacks, use `build`, then run `factory_instance.save` after the `expect`.

```
before(:each) do
  @user = Factory.build(:user)  # returns an unsaved object
  @user = Factory.create(:user) # returns a saved object
  @user = Factory(:user)        # shortcut for Factory.create()
end
```

## Testing after create callbacks with `build` and `save`:

```
describe '#send_emails' do
  context 'when stuff happens' do
    let(:person) { create :person }
    it 'sends email to person' do
      thing = build(:thing)
      expect(Email).to receive(:send_thing_to_person)
      thing.save
    end
  end
end
```
