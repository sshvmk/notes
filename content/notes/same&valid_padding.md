---
title: SAME and VALID in padding
date: 2024-05-30
tags:
  - dl
  - revisionNotes
enableToc: true
---

padding refers to the practice of adding extra pixels around the border of an input feature map. This is done to control the spatial dimensions of the output feature map after applying a convolution operation. The two most common types of padding are **"same"** and **"valid"** padding. \


**Same** padding or zero-padding, ensures that the output feature map has the same spatial dimensions (height and width) as the input feature map. This is done by adding an appropriate number of zeros to the borders of the input feature map.
$$
output size = \lceil \frac{input size}{stride}\rceil
$$

**Valid** padding means no padding is added to the input matrix. This results in the output feature map having reduced spatial dimensions compared to the input feature map after the convolution operation.
$$
output size = \lfloor {\frac{input size - filter size}{stride} } \rfloor + 1
$$