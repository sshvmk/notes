---
title: Evaluation metrics in ML
date: 2024-05-16
tags:
  - dl
  - revisionNotes
enableToc: true
---

1. Confusion matrix - A confusion matrix is an $N \times N$ matrix, where $N$ is the number of predicted classes. It is extremely useful for measuring precision-recall, Specificity, Accuracy, and most importantly, AUC-ROC curve. \
Type 1 Error = $FP$ \
Type 2 Error = $FN$
<p align="center" width="100%">
    <img width="75%" src="assets/confusionMatrix.png">
</p>

2. Accuracy - Fraction of correct predictions made by the model over the total number of predictions   
   $$ 
   Accuracy = \frac{TP + TN}{TP + TN + FP + TN}
   $$
3. Precision - The ratio of correctly predicted positive observations to the total predicted positives. It is useful when the cost of false positives is high. 
   $$ 
   Precision = \frac{TP}{TP + FP}
   $$
4. Recall (Sensitivity or True Positive Rate) - measures the fraction of true positive predictions out of the total number of actual positive instances. It is useful when the cost of false negatives is high. 
   $$ 
   Recall = \frac{TP}{TP + FN}
   $$
5. F1 score - harmonic mean of precision and recall, providing a single metric that balances both measures. It is often used in cases where both precision and recall are important. \
   $$
   F1 = \frac{2 \times (Rrecision \times Recall)}{ (Precision + Recall)}
   $$
6. ROC - AUC (Receiver Operating Characteristic - Area Under Curve)
   The ROC curve is plotted with TPR vs. FPR at various threshold settings, and the AUC represents the likelihood that the model ranks a random positive instance higher than a random negative instance.
   The AUC-ROC represents the probability that the model will rank a random positive instance higher than a random negative instance. 
7. Regression metrics 
<p align="center" width="100%">
    <img width="50%" src="assets/reggMetrics.png">
</p>

8. $R2$ $score = \frac{1 - {SS_r}}{SS_m}$
<p align="center" width="100%">
    <img width="50%" src="assets/r2.png">
</p>

