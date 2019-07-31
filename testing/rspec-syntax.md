# RSpec syntax cheetsheet



## To avoid instantiating the same object in each it block and DRY out your code:  

Using the `subject` keyword 

```
describe Thing do
 subject(:thing) {described_class.new }
  # describe blocks follow
end
```

Using before each/before all  

```
before(:each) do
 # stuff
end
```

alternatively to the before each block, use the let(:method){} like so:

```
describe 'stuff' do
 let(:your_instance_var) { block of code to execute }
 it do
 end #blocks
end
```


## The two ways to pend a test

```
describe "an example" do
 it "is implemented but waiting" do
  pending("something else getting finished")
  this_should_not_get_executed
 end
end
```

```
describe "an example" do
 xit "is awaiting implementation"
end
```