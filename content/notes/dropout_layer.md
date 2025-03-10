---
title: Dropout Layer
date: 2024-05-29
tags:
  - dl
  - revisionNotes
enableToc: true
---

Type of regularisation technique used in neural networks to prevent overfitting
During training, the dropout layer randomly sets a fraction of the input units (neurons) to zero at each update. This fraction is determined by a hyper parameter known as the dropout rate, typically set between 0.2 and 0.5.
1. **Randomly Drop Units**: For each training example, randomly select a subset of neurons and set their outputs to zero. This means these neurons are temporarily "dropped out" of the network for this training iteration.
2. **Scale Remaining Outputs**: Scale the outputs of the remaining active neurons by a factor of 1/(1−dropout rate)1/(1−dropout rate). This scaling ensures that the total input to the next layer remains consistent during training and inference
3. **Key benefits** :
    - **Regularization**: helping to prevent overfitting by introducing noise and forcing the network to learn more robust and redundant representations.
    - **Ensemble effect**: By randomly dropping out different neurons during each training iteration, dropout effectively creates an ensemble of many different sub-networks, each with a slightly different architecture. So better generalisation
    - **Sparse activations**: Dropout encourages sparse activations, meaning that only a subset of neurons are active for any given input. Improve the computational efficiency of the network during inference.