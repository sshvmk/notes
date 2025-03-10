---
title: Weight initialisation techniques
date: 2024-05-30
tags:
  - dl
  - revisionNotes
enableToc: true
---

1. Zero 
2. Random 
3. Xavier initialisation (Glorot Initialisation) \
Weights are initialised from a distribution with zero mean and a specific variance designed to keep the scale of gradients roughly the same across layers. \
    ➕ good for tanh and sigmoid \
    ➖ not good for relu 
<p align="center" width="90%">
    <img width="70%" src="assets/xavier.png">
</p>

4. He Initialisation (Kaiming Initialisation) \
Similar to Xavier initialization but with a higher variance to account for the rectified linear units (ReLU) activations. \
    ➖ can lead to exploding gradient in deep deep networks
<p align="center" width="90%">
    <img width="70%" src="assets/he.png">
</p>

5. LeCun Initialisation \
Designed for activation functions like sigmoid and tanh. \
➕ suitable for sigmoid/tanh activations \
➖ not good for relu 
<p align="center" width="90%">
    <img width="30%" src="assets/lecun.png">
</p>

6. Orthogonal Initialisation \
Weights are initialized to be orthogonal matrices \
➕ preserves the variance of the activations. \
➖ expensive computation wise 
<p align="center" width="90%">
    <img width="30%" src="assets/lecun.png">
</p>

7. Variational Initialisation \
Weights are sampled from a probability distribution, often Gaussian, and the parameters of this distribution are learned during training. \
➕ can adapt to the data during training. \
➖ more complex and requires tuning.

Few other techniques include uniform initialisation, scaled initialisation and Layer-sequential Unit-variance (LSUV) initialisation.