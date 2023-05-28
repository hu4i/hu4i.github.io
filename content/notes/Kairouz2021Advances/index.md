---
title: "Advances and Open Problems in Federated Learning"
date: 2023-05-26T09:14:45+08:00
draft: true
---

These notes are mainly taken from book of Kairouz et al., 2021 {{< cite Kairouz2021 >}}.

## 1. Introduction

### 1.1. The Cross-Device FL

{{< label federated_learning trm >}}

*Federated learning* is a machine learning setting, where

- **clients** collaborate in computing a machine learning problem
- a **central server** (or **service provider**) orchestrate the clients
- while each client's raw data is **private** and should only stored locally.

That is, the term FL is a shorthand for a set of characteristics, constrains, and challenges that often co-occur in applied ML problems on decentralized data where privacy is paramount.

{{< admonition type=quote title="Comparisons" open=true >}}

Table $1$ {{< cite Kairouz2021 6 >}} compares among *datacenter distributed learning*, cross-silo FL and cross-device in different dimensions.

{{< /admonition >}}

#### 1.1.1. Lifecycle of a Model in Federated Learning

A FL process is typically driven by a model engineer developing a model for a particular application, the typical workflow is {{< cite Kairouz2021 7>}}:

1. Problem identification
2. Client instrumentation
3. Simulation prototyping (optional)
4. Federated model traning
5. (Federated) model evaluation
6. Deployment

#### 1.1.2. A Typical Federated Training Process

A server (service provider) orchestrates the training process, by repeating the following steps until training is stopped (at the discretion of the model engineer who is monitoring the training process) {{< cite Kairouz2021 8 >}}:

1. Client selection
2. Broadcast (selected clients download the current model weights)
3. Client computation
4. Aggregation (server collects an aggregate of the device updates, stragglers might be dropped)
5. Model update

Table $2$ of a book {{< cite Kairouz2021 8 >}} gives typical order-of-magnitude sizes for the quantities involved in a typical federated learning application on mobile devices.

### 1.2. Federated Learning Research

Unlike common ML research，most researchers can only have access to simulation environment. Therefore, some suggestions for presenting FL research that addresses the open problems are to noticed {{< cite Kairouz2021 9 >}}:

- It is important to precisely describe the details of the particular FL setting of interest, particularly when  the proposed approach makes assumptions that may not be appropriate in all settings.
- When construct simulations, it is important to explain which aspects of the real-world setting the simulation is designed to capture (and which it is not),
- Privacy and communication efficiency are always first-order concerns in FL. Not to be ambiguous about *where computation happens* as well as *what is communicated*.

Appendix $A$ of a book {{< cite Kairouz2021 119 >}} summarizes some software libraries for FL simulation and standard datasets.

This chapter are notes taken from the book *Advances and Open Problems in Federated Learning* {{< cite Kairouz2021 >}}.

## 2. Relaxing the Core FL Assumptions: Applications to Emerging Settings and Scenarios

Summary: TBD.

### 2.1 Fully Decentralized / Peer-to-Peer Distributed Learning

Fully decentralized (peer-to-peer) learning's key idea is to replace communication with the server by peer-to-peer communication between individual clients. Because a reliable and powerful central server may not always be available or desirable, especially for a very large number of clients.

For comparison of FL and fully decentralized learning, see Table $3$ of the book {{< cite Kairouz2021 12 >}}.

#### 2.1.1 Algorithmic Challenges

Sources of difficulties:

- As a special case of FL with a central server;
- As an additional side-effect of being fully decentralized or trust-less.

Types of challenges:

{{< admonition type=note title="Effect of network topology and asynchrony on decentralized SGD" open=true >}}

**The instability introduced by limited conditions**:

- Background
  - Limited availability of the clients (e.g., temporarily unavailable, dropping out or joining during the execution)  
  - Limited reliability of the network  (e.g., possible message drops)  
  - ...
- Goal:
  - Algorithm should be robust under the conditions described above.
- Progress:
  - Some desired properties achieved in some special cases

**The communication delay introduced by denser network**:

- Background
  - While denser network leads to better convergence rates, it may also introduce communication delays which results in increased wall-clock time to complete each SGD iteration (when non-IID).
  - This concerns non-IID data distributions, update frequencies, efficient communication patterns and practical convergence time etc.
- Goal:
  - Solve the contradiction.
- Progress:
  - Achieved in practice when data is IID.
  - MATCHA can reduce the communication delay per iteration for any given node topology while maintaining the same error convergence speed.

**The asynchronous algorithms used by decentralized SGD**:

- Goal: Improve the async algorithms to remove the need for global synchronization and potentially improving scalability.

{{< /admonition >}}

{{< admonition type=note title="Local-update decentralized SGD" open=true >}}

**Incomplete analysis about convergence under non-IID data distributions**:

- Background:
  - Local-update decentralized SGD perform several local update steps before a communication round to reduce the communication costs (which contrasts mini-batch SGD).
- Progress:
  - Cases are proved for schemes relying on a single local update with non-IID local datasets.
  - There're some analyses about several local update steps.
  - There is an analysis involving non-IID data based on MATCHA (with local-update decentralized SGD?).

**Design of a model averaging policy that achieves the fastest convergence**.

{{< /admonition >}}

{{< admonition type=question title="IID with local-update?" open=true >}}
TBD.
{{< /admonition >}}

## Bibliography

Kairouz et al., 2021 {{< label Kairouz2021 bib >}}
: Kairouz, P., McMahan, H. B., Avent, B., Bellet, A., Bennis, M., Bhagoji, A. N., Bonawit, K., Charles, Z., Cormode, G., Cummings, R., D’Oliveira, R. G. L., Eichner, H., El Rouayheb, S., Evans, D., Gardner, J., Garrett, Z., Gascón, A., Ghazi, B., Gibbons, P. B., … Zhao, S. (2021). Advances and open problems in federated learning.

McMahan et al., 2016 {{< label McMahan2016 bib >}}
: McMahan, H. B., Moore, E., Ramage, D., Hampson, S., & Arcas, B. A. y. (2016). Communication-efficient learning of deep networks from decentralized data. International Conference on Artificial Intelligence and Statistics.
