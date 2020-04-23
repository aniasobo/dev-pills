# Tensorflow 2.0 with Keras

[Notes from A Practical Guide to Deep Learning with TensorFlow 2.0 and Keras](https://github.com/Vadikus/practicalDL)

### Jupyter

- runs with `$ jupyter notebook .` in your proj directory
- local server, runs the notebook on port `8888` by default
- runs a python interpreter
- notebooks are in markdown and can be browser-edited
- tensorflow functions can be executed in them too
- run shell commands in Jupyter by prepending them with a bang, like `!pip install bla`

### Books

- [ ] _Deep Learning With Python_ Francois Chollet (owner/maintainter of Keras) - [link to Jupyter code examples](https://github.com/fchollet/deep-learning-with-python-notebooks) - [link to Amazon](https://www.amazon.co.uk/gp/product/1617294438/)
- [ ] _Hands-on ML with Scikit-Learn, Keras & TensorFlow_ by Geron - [link to Jupyter examples](https://github.com/ageron/handson-ml2) - [link to Amazon](https://www.amazon.co.uk/gp/product/1492032646/)
- [ ] _Hands On Neural Networks with TensorFlow 2.0_ by Galeone - [link to repo](https://github.com/PacktPublishing/Hands-On-Neural-Networks-with-TensorFlow-2.0) - [link to Amazon](https://www.amazon.co.uk/gp/product/1789615550/)

### Neuron layers

- the concept of `weight` of data channels/signals that reach the neuron
- input signals \* sum of their weights + constant
- active/inactive neuron outputs `1` / `0`
- sigmoid function - ??
- same inputs processed by neurons within a neural layer (or multiple) allow us to run statistical calcs on the output
- the depth of neural layers that feed into the output is where the concept of Deep Learning came from
- performance in ML == accuracy
- convolutional neural network - not all neurons in a layer are connected to the next layer's neurons (as opposed to one where they are all connected)

### Training models

- weights and biases are random in the first step of model training
- forward propagation - processing in the neural layers outputting towards the decision
- backward propagation - reinforce the correct connection between neurons by increasing the weights by feeding back when the decision was correct; penalise the incorrect predictions by weakening the weights
- things to provide your compute with: data and algorithm/model; then the output data is fed back to the compute (backward propagation)
- data - annotated data set - the decision must be verifiable
- principle: reducing the information
- possible output - see Jupyter notebook for Creating a stylist for images

---

## Linear regression

### Jupyter notebook setup

- manual setup vs helper functions of ts
- <kbd>TAB</kbd> in Jupyter is autocomplete, showing you available funcs
- execute: <kbd>SHIFT</kbd> + <kbd>↵</kbd> - executes current snippet and opens another with cursor
- to debug - add `?` in your code/command you're about to execute, then execute

```
import tensorflow as tf // execute this line

// assign a Tensor object to a variable

var = tf.random.uniform([1])

// represent that Tensor as a numpy

print(var.numpy()) // execute
```
