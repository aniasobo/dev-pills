# RSpec mocking

## Mocking with `let`

```
let(:journey){ {entry_station: entry_station, exit_station: exit_station} }

it 'stores a journey' do
  subject.touch_in(entry_station)
  subject.touch_out(exit_station)
  expect(subject.journeys).to include journey
end
```

## Using a double with mock methods and method responses:

```
journey_class_double = double :journey, complete: true, fare: 1
```

## Mocking with singletons

[this tutorial](http://blog.testdouble.com/posts/2018-05-17-do-we-need-dependency-injection-in-ruby) 

```
# mock object

fake_object = Object.new
fake_object.define_singleton_method(:some_method) { |returned_value| false }

another_fake_object = Object.new
another_fake_object.define_singleton_method(:do_stuff) { |value| value == "some value" }

# mock objects get passed as arguments replacing dependency injections where required
```
