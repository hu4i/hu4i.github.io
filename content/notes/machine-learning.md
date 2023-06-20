---
title: "Machine Learning Note"
date: 2023-04-12T09:43:26+08:00
summary: Notes of machine learning.
draft: true
mermaid: true
---

## Introduction

Machine learning can be viewed as programming with data.

### Terminologies

{{< admonition type=note title="Basic terminologies" open=true >}}

- **Model**: the "program" learned by machine.
- **Learning**: (a.k.a. **training**) the process of obtaining desired models.
- **Learning algorithm**: the algorithm used in learning.
- **Data set**: all the information used for a training process.
- **Examples**:(a.k.a. **instances**, **samples**) is what a data set consist of.
- **Features**: (a.k.a. **covariates**, **inputs**, **attributes**) is what an example consists of.
- **Feature vector**: if every example in a data set is described by some numerical features, we say these features form a feature vector.
- **Feature values**: are the values of the corresponding features in a feature vector of an example.
- **Dimensionality**: if all the examples have the same length feature vector, we say the same is the dimensionality of the example.
- **Label**: (a.k.a. **target**) is a special attribute of which value supervised learning problem aim to predict. It is the "right" answer that a model should predict.
- **Training data** and **training example**: the data or example used in training.
- **Training set**: the set of all the training examples.
- **Objective functions**: (a.k.a. loss functions)  are the numerical functions used for judging how the good (bad) a model is. Conventionally, we assume the lower of the output of the objective function, the model is better.
- **Cost functions**

{{< /admonition >}}

{{< admonition type=warning title="Loss function and Cost function" open=true >}}

- Loss function: error for single training example
- Cost function: average of the loss functions over an entire training example
{{< /admonition >}}

{{< admonition type=note title="Some kinds of machine learning" open=true >}}

**Offline learning**:

- **Supervised learning**: if the training examples have both features and labels and the task is to produce a model which can predict label with features.
  - **Regression**: if the prediction value is continuous, we want to predict "how many a value is"
  - **Classification**: if the prediction value is discrete, we want to predict "what is the class it belongs to"
    - **Binomial classification**: (a.k.a. binary classification) if the prediction has two categories
      - **Positive class** and **Negative class**: we usually designate one class as positive and another as negative.
    - **Multi-class classification**: if more than two categories
  - **Multi-label classification**: if the classes are not mutually exclusive, we want to predict "what are the classes it belongs to" or "tag it"
  - ...
- **Unsupervised learning**: if the training examples don't have labels and
  - **Clustering**: group the training examples into groups.
    - **Cluster**: every group is called a cluster.
  - **Subspace estimation**: find a small number of parameters that accurately capture the relevant properties of the data.
    - **Principal component analysis**:  If the dependence is linear.
  - ...
**Online learning**:
- **Reinforcement Learning**: if the task is to develop a model that can interact with an environment and take actions.

{{< /admonition >}}

## Federated Learning

### Parallel Computing for ML

#### MapReduce: Synchronous Parallel Gradient Descent

- MapReduce: a programming model and software system developed by Google
  - chara.: client-server (worker-server) arch., mesg-passing comm., bulk syn. parallel.
- Apache Hadoop: open-source impl. of MapReduce
- Apache Spark: an improved open-source impl. of MapReduce

Basic operations:

- Broadcast: S -> W
- Map: W-> W
- Reduce: W -> S

Problem:

- time of comm. and syn.
  - comm.
    - comm. complexity: how many words are trans. between S and W.
      - prop. to num. of param.
      - grow th num of W nodes.
    - latency
    - comm. time = (complexity / bandwidth) + latency
  - syn. time
    - node fails and restart. (straggler node)
- speedup ratio: (wall clock time using one nodes) / (wall clock time using m nodes)
  - idea: linear function
  - actual: log-like function

#### Parameter Server: Asynchronous Parallel Gradient Descent

Parameter Server

- c-s arch., msg-passing comm., async.
- Ray: open-source software system, supports parameter server.

Pro and Com

- faster
- low async. rate

### Decentralized Network: P2P Parallel Gradient Descent

- chara: p2p arch. msg-passing comm
- pass $w$ and average it
- convergence rate depends on how well the nodes are connected

### Parallel Computing and Distributed Computing

- Distributed computing is a kind of parallel computing
- It is not black and white. No consensus in the academia
- HPC people's opinion:
  - When the compute nodes are not in the physical locations, parallel computing is called distributed computing
- ML people's opinion:
  - When the data or model are partitioned among multiple nodes, parallel computing is called distributed computing.
  - In contrast, computation in one node(which has many processors) is not distributed computing.

### Parallel Computing in TensorFlow

pass

### Federated learning vs distributed learning

1. Users have control over their device and data
2. Worker nodes are unstable
3. Communication cost is higher than computation cost
4. Data stored on work nodes are note IID
5. The amount of data is severely imbalanced

### Research Direction

Main problem: IID is required

1. Communication cost  
  Federated averaging algorithm: $w$ are sent between S and W.
    - loss reducing measured by comm.: Federated averaging is faster than grad descent.
    - loss reducing measured by epochs: grad descent is faster
2. Privacy
  $g$ may leak users' privacy
3. Adversarial Robustness
