---
title: "Pytorch Notes"
date: 2023-04-12T20:09:36+08:00
summary: Notes of Pytorch.
draft: true
---

## Official Tutorial

- [PyTorch official tutorial](https://pytorch.org/tutorials/beginner/basics/intro.html)

### Tensors

- Pytorch use tensors to encode the inputs and outputs of a model, as well as the model’s parameters.
- Pytorch's tensors is implemented on **NumPy’s ndarrays**, the only difference is the former can run on GPU.
- Every operation on tensors can be **run on the GPU**
  - By default, they are run on the CPU. We need use move tensors to the GPU using `.to` method of tensors.
  {{< admonition warning "Warning" true >}}
  - Copying large tensors across devices can be expensive.
  - Remember to check GPU's usability.
  {{< /admonition >}}
- Operations that store the result into the operand are called **in-place**. They are denoted by a `_` suffix like `tensor.add_(5)`.
  {{< admonition warning "Warning" true>}}
  When computing derivatives, in-place operation can cause an immediate loss of history. Their use is discouraged.
  {{< /admonition>}}
- When using `.numpy()` or `.from_numpy()` methods to convert between tensors and NumPy arrays, remember:
  {{< admonition warning "Warning" true>}}
  Changes in tensor or NumPy array will reflect to each other. See [Bridge with NumPy](https://pytorch.org/tutorials/beginner/basics/tensorqs_tutorial.html#bridge-with-numpy)
  {{< /admonition>}}

### Datasets & Dataloaders

- PyTorch provides two libraries to process data samples:
  - `torch.utils.data.Dataset`: stores the sample and their corresponding labels
  - `torch.utils.data.DataLoader`: wraps an iterable around the `Dataset` to enable easy access to the samples
- It alse provides some pre-loaded datasets and its relating implemented functions for easy use. They can be used to prototype and benchmark our models.

### Transformers

- We need to use transformers to manipulate the data and make it suitable for tarining. TorchVision datasets have two parameters:
  - `transform` to modifies the features
  - `target_transform` to modify the labels
- `torchvision.transforms` module offers several commonly-used transforms.

### Build The Neural Network

- PyTorch provides `torch.nn` that contains all the building block to build a neural network.
- A neural network is a module and it consits of other modules, we call the modules inside a neural network layers.
  - Every module in PyTorch is subclasses the `torch.nn.Module`

### Automatic Differentiation With `torch.autograd`

- **Back propagation** is an algorithm in neural network, parameters are adjusted according to the **gradiant** of the loss function with respect to the given parameter.
- PyTorch provide  a differentiation engine named `torch.autograd` to automatically compute the gradient for any computational graph.

## Data Manipulation

### Tensor

#### Create new tensors

- Initialized with parameters
  - torch.arange
  - torch.zeros((2, 3, 4))
  - torch.ones((2, 3, 4))
  - torch.randn(3, 4)
- From existing tensors
  - x.reshape
    - automatically infer
  - torch.cat
- From ohter object
  - From NumPy: B = torch.from_numpy(A)

{{< admonition type=warning title="Concatenate mechanism" open=false >}}
{{< /admonition >}}

#### Indexing and Slicing

- The same operation of indexing and slicing tensor as with python list.

{{< admonition type=warning title="Assigning multiple elements the same value" open=false >}}
{{< /admonition >}}

#### Operations

{{< admonition type=warning title="Lifting mechanism" open=false >}}
{{< /admonition >}}

#### Get properties

- `x.numel()`
- `x.shape`
- `x == y` (elementwise)
- `x.sum`

### Broadcasting

{{< admonition type=warning title="Broadcasting mechanism" open=false >}}
{{< /admonition >}}

### In-place operation

- x[:] = x + y
- x+=y
- (while x = x + y is not in-place)

{{< admonition type=warning title="Memory management" open=false >}}
{{< /admonition >}}

### Conversion

- To scalar:
  - pytorch's item function: x[0].item
  - python's built-in function: int(x[0])
- To NumPy: A = X.numpy()

## Autograd

The `torch.autograd` is PyTorch’s automatic differentiation engine used for neural network training.

- Official tutorial: [A GENTLE INTRODUCTION TO TORCH.AUTOGRAD](https://pytorch.org/tutorials/beginner/blitz/autograd_tutorial.html)
- Some details about `backward` function: [The “gradient” argument in Pytorch’s “backward” function — explained by examples](https://zhang-yang.medium.com/the-gradient-argument-in-pytorchs-backward-function-explained-by-examples-68f266950c29)
