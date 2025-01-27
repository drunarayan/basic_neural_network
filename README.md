# Basic Neural Network Library
# The Bush School CPJava final project 2022

This is a very basic Java Neural Network library based on the one built by Daniel Shiffman in [this](https://www.youtube.com/watch?v=XJ7HLz9VYz0&list=PLRqwX-V7Uu6aCibgK1PTWWu9by6XFdCfh) playlist using the [Efficient Java Matrix Library](https://www.ejml.org) (EJML).

The library can also be used with [Processing](https://processing.org). Just download the jar-file (see below) and drag it into your sketch.

If you want to learn more about Neural Networks check out these YouTube-playlists:
- [Neural Networks - The Nature of Code](https://www.youtube.com/watch?v=XJ7HLz9VYz0&list=PLRqwX-V7Uu6aCibgK1PTWWu9by6XFdCfh) by The Coding Train (Daniel Shiffman)
- [Neural Networks](https://www.youtube.com/watch?v=aircAruvnKk&list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi) by 3Blue1Brown
 
## Features

- Neural Network with variable amounts of inputs, hidden nodes and outputs
- Multiple hidden layers
- Activation functions: Sigmoid, Tanh, ReLu
- Adjustable learning rate
- Fully connected
- Support for genetic algorithms: copy-, mutate-, and merge-functionality
- Save the weights and biases of a NN to a JSON-file
- Generate a NeuralNetwork-object from a JSON-file

## Getting Started

## Use the library

Constructors:
```java
// Neural network with 2 inputs, 1 hidden layer, 4 hidden nodes and 1 output
NeuralNetwork nn0 = new NeuralNetwork(2, 4, 1);

// Neural network with 2 inputs, 2 hidden layers, 4 hidden nodes and 1 output
NeuralNetwork nn1 = new NeuralNetwork(2, 2, 4, 1);
```

Train and guess:
```java
// Train the neural network with a training dataset (inputs and expected outputs)
nn.train(trainingDataInputs, trainingDataTargets);

// Guess for the given testing data is returned as an array (double[])
nn.guess(testingData);
```

Read and write from/to file:
```java
// Reads from a (previously generated) JSON-file the nn-Data and returns a NeuralNetwork-object
NeuralNetwork myNN = NeuralNetwork.readFromFile();
// Load from a specifiy file (by default it will look for a file called "nn_data.json")
NeuralNetwork myNN = NeuralNetwork.readFromFile("my_nn_data.json");

// Writes a JSON-file with the current "state" (weights and biases) of the NN
myNN.writeToFile();
// Specify a custom file name (by default it will be saved as "nn_data.json")
myNN.writeToFile("my_nn_data");
```

Adjust the learning rate:
```java
// Set the learning rate (Initially the learning rate is 0.1)
nn.setLearningRate(0.01);

// Get current learning rate
nn.getLearningRate();
```

Use different activation functions:
```java
// Set the activation function (By default Sigmoid will be used)
nn.setLearningRate(ActivationFunction.TANH);

// Get name of currently used activation function
nn.getActivationFunctionName();
```

Use this library with genetic algorithms:
```java
// Make an exact and "independent" copy of a Neural Network
NeuralNetwork nn2 = nn1.copy();

// Merge the weights and biases of two Neural Networks with a ratio of 50:50
NeuralNetwork merged = nnA.merge(nnB);

// Merge the weights and biases of two Neural Networks with a custom ratio (here: 20:80)
NeuralNetwork merged = nnA.merge(nnB, 0.2);

// Mutate the weights and biases of a Neural Network with custom probability
nn.mutate(0.1);
```
More detailed examples can be found below.

## Download

If you want to use this library you can download [v0.5](https://github.com/drunarayan/basic_neural_network/releases/download/v0.5/basic_neural_network-v0.5.jar) here.

## Examples

- TBD

## Libraries & Tools used in this project

- [EJML](https://www.ejml.org) used for Matrix math
- [Google Gson](https://github.com/google/gson) library
