# The two schools of TDD: London vs Chicago

[London school vs Chicago school of TDD](http://programmers.stackexchange.com/questions/123627/what-are-the-london-and-chicago-schools-of-tdd)

```
# London Style
describe Order do
  let(:menu) { double :menu, price: '£1.00', contains?: true }
  subject(:order) { described_class.new(menu) }

  it 'order total to be sum of items added' do
    order.add('Pizza')
    order.add('Pizza')
    expect(order.total).to eq '£2.00'
  end
end
```

```
# Chicago Style --> arguably an 'integration' or 'feature' test
describe Order do
  subject(:order) { described_class.new(Menu.new) } # note real Menu class

  it 'order total to be sum of items added' do
    order.add('Pizza')
    order.add('Pizza')
    expect(order.total).to eq '£2.00'
  end
end
```
