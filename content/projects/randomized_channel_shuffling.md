---
title: Randomized Channel Shuffling, Minimal-Overhead Backdoor Attack Detection without Clean Datasets
description: 
toc: true
authors:
  - Ruisi Cai
tags:
categories:
series:
date: '2022-09-23T19:41:22-05:00'
lastmod: '2022-09-23T19:41:22-05:00'
featuredImage:
draft: false
---

Deep neural networks (DNNs) typically require massive data to train on, which is a hurdle for numerous practical domains. Facing the data shortfall, one viable option is to acquire domains-specific training data from external uncensored sources, such as the open web or the third-party data collectors. However, the quality of such acquired data is often not rigorously scrutinized, and one cannot easily rule out the risk of "poisoned" examples being included in such unreliable datasets, resulting in unreliable models which pose potential risks to many data-hungry, or high-stake applications. Existing methods usually suffer from high computational cost and unrealistic assumption on the access of clean data.

In contrast, this paper achieve to detect backdoors for victim models with limited prior knowledge: in particular, for one unreliable model, users (1) have no prior knowledge whether it is poisoned, or on the target class/percentage of poisoned samples, and (2) have no access to a clean sample set from *the same domain distribution*, nor any trusted model trained on such clean data. 

We investigate the contrasting channel-level statistics between backdoor trigger and clean features, and consequently, how the former can be differentiated by progressive channel shuffling.
Based on it, we propose the randomized channel shuffling method for backdoor-targeted class detection, which requires only a few feedforward passes and thus incurs minimal overheads, and demands no clean sample nor prior knowledge, while the identified target class help accelerate trigger recovery by highlighting the classes of interest.

Extensive experiments are conducted with three datasets (CIFAR-10,  GTSRB, TinyImageNet), three architectures (AlexNet, ResNet-20, SENet-18), and three strong attacks (BadNets, clean label attack, and WaNet). Results consistently endorse the effectiveness of our technique in backdoor model detection,  with margins of $0.291\sim 0.640$ AUROC over the current state-of-the-art methods. Codes will be released.
