# Javascript-FacadeCNN

This repository provides a browser-based Convolutional Neural Network (CNN) implementation in JavaScript with a full facade API for introspection and runtime modification. The system is designed for learning, teaching, and detailed exploration of CNN architecture, data flow, and training dynamics—entirely client-side, without external dependencies.

---

## Table of Contents

- [About](#about)
- [Features](#features)
- [Getting Started](#getting-started)
- [Basic Example](#basic-example)
- [Facade API](#facade-api)
- [Usage Notes](#usage-notes)
- [License](#license)

---

## About

Javascript-FacadeCNN is an interactive web application that lets you build, train, and explore convolutional neural networks in the browser.  
The built-in facade API exposes all internal states and parameters of the model—including feature maps, kernels, gradients, activations, pooling indices, logits, softmax outputs, and more.

Typical use cases include:
- Technical demonstrations of CNN concepts (convolution, pooling, feature extraction, backpropagation, gradient flow)
- Step-by-step experiments in computer vision
- Live model editing and debugging for understanding and ablation

---

## Features

- Interactive network configuration:
  - Adjustable input size (width, height, channels)
  - Arbitrary number and size of convolutional layers (filters, kernel sizes, strides, padding)
  - Pooled layers with customizable pool size
  - Fully connected (dense) layers after flattening
  - Configurable output size (number of classes)
  - Activation function: ReLU (internally)
- Training and optimization:
  - Cross-entropy loss with softmax output
  - Configurable learning rate, batch size, dropout rate
  - Optimizer: SGD or Adam (selectable)
  - Progress bar and training log with loss tracking
  - Save and load model state in-browser
- Dataset management:
  - Built-in synthetic dataset generator for rapid testing (class segmentation, noise)
  - Dataset preview and inspection
  - Batch training and evaluation routines
- Model inference and evaluation:
  - Input image preview and randomization
  - Per-class performance metrics reporting
  - Prediction per current input
- Full introspection and manipulation via Facade API:
  - Inspect/modify convolutional feature maps, kernels, biases, pooling, FC layers
  - View/alter activations, gradients, optimizer internals (moments, learning rates)
  - Filter/feature saliency and deconvolution tools
  - Histogram and statistics tools (activation, weight distributions)
  - Dynamic structural modifications (add/remove filters or layers at runtime)
  - BatchNorm and attribute (tag/key) editing per filter
- All browser-based, no installation, no dependencies

---

## Getting Started

### Requirements

- A modern web browser (Chrome, Firefox, Edge, Safari, etc.)

### Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/matthewJamesAbbott/Javascript-FacadeCNN.git
    ```
2. Open `index.html` in your browser.

_No build step or server is required._

---

## Basic Example

Spin up a quick CNN classifier in-browser:

1. Open `index.html`
2. In **Network Configuration**:
    - Set input: `Width=28`, `Height=28`, `Channels=1`
    - Conv Filters: `8,16`
    - Kernel Sizes: `3,3`
    - Pool Sizes: `2,2`
    - FC Sizes: `64`
    - Output Classes: `10`
    - Learning Rate: `0.001`
    - Dropout Rate: `0.25`
    - Optimizer: `Adam`
3. Click **Create Network**
4. Generate a synthetic dataset (default samples/class)
5. In **Training**, set epochs and batch size, then click **Train**
6. Use **Evaluate** or **Predict Current Image** after training
7. Explore the **CNN Facade API Explorer** section to inspect, modify, or visualize internal network state and structure

---

## Facade API

The Facade API enables stepwise access to the full internal state of all CNN layers:

- Feature map access: inspect or overwrite activations per layer/filter
- Pre-activation inspection and editing
- Kernel and bias extraction and assignment; visualize all kernels
- Batch activations, flattening, and output logits/softmax
- Pooling indices, dropout and batchnorm parameter queries and mutation
- Gradient and optimizer state inspection (Adam moments, weight/bias gradients)
- Filter and layer modification (add/remove) at runtime for ablation studies or custom topologies
- Layer statistics, histograms (activation, weights)
- Saliency map and deconvolution for feature visualization
- Receptive field and attribute metadata for model analysis or tagging

API controls are available directly from the web UI. Output and results are shown in the Facade Output pane and relevant visualizations panels.

---

## Usage Notes

- Tool is designed for didactic, moderate-sized CNNs suitable for browser memory and CPU—(for larger models, use batch size/epoch/structure adjustments)
- Synthetic data generation and visualization is included for demonstration and rapid experimentation
- All changes are in-memory; to save or reload models, use the provided save/load options
- Works without GPU or external dependencies

---

## License

MIT License.  
Open for use, modification, and distribution in any educational, research, or technical setting.

---

## Vercel Link

https://javascript-facade-cnn.vercel.app/
