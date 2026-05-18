# MNIST Digit Classification From Scratch in C++

## Overview

This project is a hand-crafted neural network implementation in C++ for handwritten digit classification using the MNIST dataset.
The system was developed entirely from scratch without using machine learning or numerical computation libraries such as TensorFlow, PyTorch, OpenCV, Eigen, or OpenNN.

The project focuses on low-level neural network implementation, training mechanics, mathematical understanding, and real-time visualization using SFML.

---

## Features

* Fully custom neural network implementation in C++
* Manual implementation of:

  * Forward propagation
  * Backpropagation
  * Gradient descent
  * Softmax activation
  * Cross-entropy loss
  * Sigmoid activation
* MNIST handwritten digit recognition
* Real-time testing and visualization using SFML
* Weight and bias serialization system
* Training mode and visual testing mode
* State-driven application architecture
* Custom resource management system
* Configurable learning parameters

---

## Technologies Used

* C++
* SFML
* STL (Standard Template Library)
* Visual Studio

---

## Project Structure

```text
root/
│
├── External/
│   └── Sfml/
│
├── ImageDetectionCNN/
│   │
│   ├── Asset/
│   │   └── Images and application assets
│   │
│   ├── CNN/
│   │   └── Neural network implementation
│   │
│   ├── Data/
│   │   └── Stored weights and biases
│   │
│   ├── FileHandling/
│   │   └── File read/write utilities
│   │
│   ├── ImageRead/
│   │   └── Image preprocessing and pixel conversion
│   │
│   ├── Resource/
│   │   └── Resource manager for fonts and assets
│   │
│   ├── States/
│   │   ├── Training state
│   │   ├── Visual testing state
│   │   └── State manager
│   │
│   ├── Utility/
│   │   └── Constants, configs, and utility helpers
│   │
│   └── Main application source
```

---

## Neural Network Architecture

```text
Input Layer → Hidden Layer → Output Layer
```

| Layer        | Description                                    |
| ------------ | ---------------------------------------------- |
| Input Layer  | Flattened MNIST image pixels                   |
| Hidden Layer | Fully connected layer using sigmoid activation |
| Output Layer | Softmax classification layer for digits 0–9    |

---

## Core Learning Pipeline

### Forward Propagation

The network performs:

* Weighted matrix summation
* Bias addition
* Sigmoid activation
* Softmax normalization

Implemented in:

* `Convulation()`
* `ConvulationWithSoftmax()`

---

### Loss Function

Cross-entropy loss is used for classification error calculation.

Implemented in:

* `TotalCost()`
* `CostForSigmoid()`

---

### Backpropagation

Gradient errors are manually propagated backward through the network.

Implemented in:

* `BackPropError()`
* `ActivationCost()`

---

### Weight Optimization

Weights and biases are updated using gradient descent.

Implemented in:

* `UpdateWeightAndBias()`

---

## Application Modes

### Training Mode

* Loads MNIST training data
* Performs forward and backward propagation
* Updates weights and biases
* Saves learned parameters

### Visual Testing Mode

* Loads trained weights
* Displays image predictions visually
* Shows probability outputs in real time

---

## Data Persistence

The application stores:

* Hidden layer weights
* Hidden layer biases
* Output layer weights
* Output layer biases

This allows the model to continue training without restarting from random initialization.

---

## Accuracy

The neural network achieved approximately **95% accuracy** on MNIST digit classification through manual implementation and optimization.

---

## Educational Goals

This project was built to understand:

* Neural network mathematics
* Backpropagation mechanics
* Activation functions
* Gradient descent optimization
* Numerical stability in softmax
* Low-level AI implementation in C++
* Real-time AI visualization systems

---

## Future Improvements

* True convolutional layers
* Pooling operations
* ReLU activation
* Mini-batch training
* GPU acceleration
* Better image preprocessing
* Dynamic network architecture
* Parallelized computation

---

## Important Note

Despite the class name `CNN`, the current implementation is a fully connected feedforward neural network and does not yet include true convolution kernels or pooling layers. The project was created primarily for educational and architectural learning purposes.
