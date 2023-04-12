---
title: "Machine Learning Note"
date: 2023-04-12T09:43:26+08:00
draft: true
mermaid: true
---

## Introduction

Machine learning can be viewed as programming with data. In programming, we design a program that can calculate the input and give us the corresponding output. In machine learning,
the **model** is the program that can predict some output from our input. What's the difference is that we use a learning algorithm to feed the model with some examples. The
**learning algorithm** teaches the model how to learn from the examples and use **objective functions** to judge if the model is a "good student" who can do other similar stuffs rather
than only the given examples.

### Key concepts

Here are (may non-formal) definition of some basic terminologies:

- **learning**: (a.k.a. **training**) the process of obtaining desired models.
- **model** and **learning algorithm**: see the description in introduction above.
- **Data set**: is all the information used for a training process.
- **Examples**:(a.k.a. **instances**, **samples**) is what a data set consist of.
- **Features**: (a.k.a. **covariates**, **inputs**, **attributes**) is what an example consists of. If every example in a data set is described by some numerical features, we say these features form a feature vector.
- **Feature values**: are the values of the corresponding features in a feature vector of an example.
- **Dimensionality**: if all the examples have the same length feature vector, we say the same is the dimensionality of the example.
- **Label**: (a.k.a. **target**) is a special attribute of which value supervised learning problem aim to predict.
- **Training data** and **training example**: the data or example used in training.
- **Training set**: the set of all the training examples.
- **Objective functions**: (a.k.a *loss functions.*) are the numerical functions used for judging how the good (bad) a model is. Conventionally, we assume the lower of the output of the objective function, the model is better. So it is also called a loss function.
  
### Some Kinds of Machine Learning

**Offline learning**:

- **Supervised learning**: if the training examples have both features and labels and the task is to produce a model which can predict label with features.

  - **Regression**: if the prediction value is continuous, we want to predict "how many a value is"
  - **Classification**: if the prediction value is discrete, we want to predict "what is the class it belongs to"
    - **Binomial classification**: (a.k.a. binary classification) if the prediction has two categories
      - **Positive class** and **Negative class**: we usually designate one class as positive and another as negitive.
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
  
  {{< admonition quote "Reference" true >}}
  Quote forom [Dive into Deep Learning](https://d2l.ai/chapter_introduction/index.html#reinforcement-learning):
  > Reinforcement learning gives a very general statement of a problem, in which an agent interacts with an environment over a series of time steps. At each time step, the agent receives some observation from the environment and must choose an action that is subsequently transmitted back to the environment via some mechanism (sometimes called an actuator). Finally, the agent receives a reward from the environment. This process is illustrated in Fig. 1.3.7. The agent then receives a subsequent observation, and chooses a subsequent action, and so on. The behavior of a reinforcement learning agent is governed by a policy. In short, a policy is just a function that maps from observations of the environment to actions. The goal of reinforcement learning is to produce good policies.

  ```goat
                         ┌────────┐
      ┌─────────────────►│ Action ├──────────────────────┐
      │                  └───┬────┘                      │
      │                      │                           │
      │                      ▼                           ▼
  ┌───┴───┐               ┌──────┐                 ┌───────────┐
  │ Agent ├───────────────┤Reward│◄────────────────┤Environment│
  └───────┘               └──────┘                 └─────┬─────┘
      ▲                                                  │
      │                                                  │
      │                 ┌───────────┐                    │
      └─────────────────┤Observation│◄───────────────────┘
                        └───────────┘

                          Fig.1.3.7
  ```

  {{< /admonition >}}