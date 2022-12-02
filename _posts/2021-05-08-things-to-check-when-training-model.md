---
toc: true
layout: post
description: My first blog post using markdown with fastpages.
categories: [deep learning]
title: Things to check when I train a model.
---

According to the research mentioned in book [‘Mastermind: How to Think Like Sherlock Holmes’ by Maria Konnikova](https://amzn.to/3aW7zCz), even highly skilled professions like medical doctors are prone to errors and forget important steps in their work if they don't have written guidance or recepe to do routine repetitive tasks.

So, I decided to write down a list of things that I should check to avoid ruining experiments and save time.

1. Check that optimizer and learning rate (SGD, Adam, etc.) is exactly what you need and not old values from previous experiments.
2. Check train and validation augmentations
3. Check number of epochs to train
4. Check if the model is pre-trained or you resume from trained checkpoint. If resume, lower lr (if you don't use lr scheduler for # epoch)
5. Check that model is frozen\unfrozen like you need.
6. Check dataset. Most of the cases in real world data it is not balanced, so do over- and undersampling. If it is production data - pull latest updates.
7. Check batch size, num_workers for data loader, cuda # if you have > 1 GPU.
8. Check the experiment name for logging. I use ClearML(https://clear.ml/) at work and can recommend them for friendly slack community.

Also inspired by https://twitter.com/karpathy/status/1013244313327681536
Update: more [detailed article](https://karpathy.github.io/2019/04/25/recipe/) by Andrej
