# FactoryBot - `let` vs `let!`

- Factories created with `let` only come to existence when they're **referred to**.
- Factories created with `let!` come into existence every time.
- `let` and `let!` can only be called in a `context`/`describe` block and not an `it` block; create variables within `it` blocks with regular variable assignment - see [the refactoring section](../testing/factorybot.md#refactoring)

```
context 'thing' do
  let!(:shift1) { create(:shift) } ### always gets created when suite runs
  let(:shift2) { create(:shift) }
  let(:expensive_to_create_thing) { create(:expensive_thing) } ### never use ! for creating those, unless used often in suite

  it 'does something' do
    Shift.all.size          ### 1 shift exists because shift2 is not being referred to
  end

  it 'does something else' do
    shift2                  ### shift2 reference creates it
    Shift.all.size          ### we now have 2 shifts in existence!
  end

  it 'does something with the expensive thing' do
    expensive_to_create_thing.blah    ### one use of the expensive thing so gets created here only once, not slowing other tests down
  end
end
```
