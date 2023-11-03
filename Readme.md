# LAIbrary

![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg) [Open In Colab](https://colab.research.google.com/github/IGieckI/LAIbrary/blob/main/LAIbrary.ipynb)

# !!! STILL WORK IN PROGRESS !!!

Welcome to LAIbrary, a Python library designed to provide a highly customizable and extensible framework for building and training neural networks. It empowers you to create neural networks with personalized neurons, different learning rates, and various activation functions, all while maintaining a clear and hierarchical structure.

## Features

- **Customizable Neurons**: LAIbrary allows you to customize each neuron in your network. You can define different learning rates, activation functions, and more for individual neurons, providing a lot of flexibility.

- **Hierarchical Structure**: LAIbrary supports a hierarchical structure with neurons, layers, and networks. This hierarchy enables you to design complex neural networks with ease.

- **Pipelining Between Networks** (Planned): LAIbrary's future implementation will allow you to create pipelines between multiple networks, facilitating the development of multi-stage models.

## Neural Network Layer Implementation Checklist

- [x] Input Layer (TO BE MADE MORE CUSTOMIZABLE)
- [x] Dense Layer (Fully Connected Layer)
- [ ] Convolutional Layer
- [ ] Pooling Layer
- [ ] Recurrent Layer
- [ ] Long Short-Term Memory (LSTM) Layer
- [ ] Gated Recurrent Unit (GRU) Layer
- [ ] Embedding Layer
- [ ] Batch Normalization Layer
- [ ] Dropout Layer
- [x] Output Layer (TO BE MADE MORE CUSTOMIZABLE)
- [x] Softmax Layer

## Usage

LAIbrary is designed to be highly customizable, and you can use it to create your own neural networks. You can start by adding layers to your network, specifying their characteristics, and training your network.

Here is an example of how you can use LAIbrary to create and train a simple neural network:

```python
x_train = [...]
y_train = [...]

# Create a neural network
net = Network(MeanSquaredError())
net.add_layer(FullyConnectedLayer(2, 50))
net.add_layer(ActivationLayer(Tanh()))
net.add_layer(FullyConnectedLayer(50, 50))
net.add_layer(ActivationLayer(Tanh()))
net.add_layer(FullyConnectedLayer(50, 1))
net.add_layer(ActivationLayer(Tanh()))

# Train the network
net.train(x_train, y_train, epochs=100, learning_rate=0.1)

# Test the network
out = net.predict(x_train)
print(out)
```

## TODO
- Make all activation functions static so that you don't have to recreate the object every time.
- Change the return values of most of the activation functions (not compatible with the new network)
- Implement the listed new layers
- Implement a pipeline to "merge" multiple networks
- Implement paralization for computing efficency (GPU usage)
