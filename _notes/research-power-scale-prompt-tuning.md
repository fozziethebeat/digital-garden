---
title: "The Power of Scale for Parameter-Efficient Prompt Tuning"
excerpt: Tuning prompt vectors works better than hacking text prompts
---

This [[Research]] [paper](https://aclanthology.org/2021.emnlp-main.243.pdf)
compares three ways of tuning a model:

1.  Task Tuning whereby all parameters are updated (Standard Practice)
1.  Tuning Task Prompts with full text inputs (Open-AI favored)
1.  Tuning prompt vectors (New)

They find that in the right settings, tuning vector prompts rather than text
prompts approaches full task parameter tuning and is generally more efficient
for training.  Overall they show that this approach saves mdoel storage and
serving costs and provides simpler options for ensembling.

