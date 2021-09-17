---
title: "Towards Universality in Multilingual Text Rewriting"
excerpt: Adapting mT5 to fit different text styles
tag:  [[Research]]
---

This [[Machine Translation]] [[Research]]
[paper](https://arxiv.org/pdf/2107.14749.pdf)
demonstrates how to modify a bilingual multilingual encoder decoder network to
change the style of format of content using example sentences.

This follows on some previous [work](https://arxiv.org/abs/2010.03802) with
some tweaks to force multi-lingual support and some simplifications.  They in
brief modify the ecoder's embedding inputs with a multi-step process:

  - Take a sequence of sentences that are assumed to have the same "style"
  - Corrupt the second sentence to have either missing words or changed words
  - Produce a "style" vector by prepending some `<2style>` type token to the
    first sentence and running it through the encoder.
  - Mixing the embedding of the first sentence with first embedding of the first sentence.
  - Reproducing an uncorrupted version of the second sentence along with an
    English translation of the sentence (using parallel data).

This modifies the original work in two key ways:

  - The encoder network is the same for both input sentences
  - The decoder is expected to also translate

Both of these changes seem to encourage the model to do cross language style
transfer with few examples.

