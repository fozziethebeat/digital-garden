---
title: "Self-supervised and Supervised Joint Training for Resource-rich Machine Translation"
excerpt: Bayesian model inferring trust of annotators
tag:  [[Research]]
---

This [[Machine Translation]] [[Research]]
[paper](https://arxiv.org/pdf/2106.04060.pdf) demonstrates how to train high
end and high resource language pairs with parallel and monolingual data.  They
extend an approach for low resource languages that innovates using
encoder-decoder cross over techniques.

Briefly, the paper produces data by:
  - Preparing monolingual data with two flavors: masked input to reproduce the
    original output and noised input to reproduce the original output.
  - Preparing regular bilingual data.
  - The two types of monolingual data get blended together with a crossover
    encoder-decoder network that produces a mixed embedding representation and
output Ids.
  - The blended monolingual data is then blended with the bilingual data to
    again produce mixed embedding representations and output IDs.
  - The model then trains on that final second stage blended embeddings.

The model improvements are impressive.  It produces the new state of the art in
a very competitive open evaluation.  The approach also doesn't look too
complicated to produce even though it does slow down training by a noticable
amount (20% drop in training time even with optimizations).
