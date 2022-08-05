---
toc: true
layout: post
description: General rules to debug DL models.
categories: [deep learning]
title: Things to check when I test a model.
---

This is logical continuation of my first blogpost about Training the model {% post_url 2021-05-08-things-to-check-when-training-model %}.

Some times when testing new models with validation accuracy >90%, test accuracy can be < 0.1%. This is pretty strong signal that there is a bug in testing. I would like to list most common ones, in order to eliminate them fast next time something is not working.

1. When the results are close to 0:
    - Loaded model is in eval mode.
    - Input normalized the same way it was in training.
2. When the results are bad but not 0:
    - Validate on balanced data, so the long tail classes won't screw the accuracy.
3. If you aim for accuracy and don't have inference time constraints:
    - Use test time augmentation.
    - Consider model ensemble from multiple checkpoints
