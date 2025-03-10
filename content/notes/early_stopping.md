---
title: Early Stopping
date: 2024-05-29
tags:
  - dl
  - revisionNotes
enableToc: true
---

regularisation technique used in training deep neural networks to prevent overfitting. It works by monitoring a validation metric (e.g., validation loss or accuracy) during the training process. If the validation metric stops improving for a certain number of epochs (called the "patience" parameter), the training is stopped early, even before the maximum number of epochs is reached.
>Patience - number of epochs with no improvement after which training will be stopped

As the training progresses, the model initially learns the underlying patterns in the data, and the validation metric improves. But after a certain point, the model starts to overfit to the training data, and the validation metric begins to degrade. By stopping the training at this point, early stopping helps to prevent overfitting and can improve the generalisation performance of the model on unseen data.