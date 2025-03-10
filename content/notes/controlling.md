---
title: Controlling temp, top_p and top_k
date: 2024-05-16
tags:
  - dl
  - llm
enableToc: true
---

## Controlling temp, top_p and top_k

So I have been working on a TTS model and for the last few days I am playing with few hyperparameters. In my specific use case, I found that temperature, top_p and top_k played a major role in audio generated.

### temperature

helps control the randomness / creativity of the model. Basically you adjust the probabilities to force randomness or determinism. During training the temperature is 1. Mathematically, when the probability of next token is being calculated the model will divide that by your temperature value.

<!-- {{< katex display=true >}} -->

$$
\text{softmax}(x_i; T) = \frac{e^{\frac{x_i}{T}}}{\sum_{j} e^{\frac{x_j}{T}}}
$$

<!-- {{< /katex >}} -->

Python function of softmax with temperature :

    def softmax_with_temperature(logits, temperature=1.0):
        logits /= temperature
        exp_logits = np.exp(logits - np.max(logits))  # subtracting max for numerical stability
        softmax_output = exp_logits / np.sum(exp_logits)
        return softmax_output

### top_p

top*p selects most likely token from a prob distribution, considering cumulative probability until it reaches a predefined threshold \_p*. In other words, only consider the possibilities that equal or exceed this value. Value of this parameter ranges from 0.0 to 1.0

### top_k

this selects _k_ most likely options (depending on their probabilities). So token with very low probability are not selected which makes output more coherent. I have found that changing top_p and temp is more useful than trying to tweak top_k.

> [!note] _When we set the temperature to 0, choose only the top 1 token (K=1), or the probability threshold to 0 (P=0), it's like swapping out the softmax with a simple maximum selection formula. This means we're only focusing on the single most probable next token and ignoring everything else._
