+++
title = "🇮🇹🇯🇵🇧🇷 Generating multilingual instruction datasets with Magpie 🐦‍⬛"
date = "2024-10-21"
description = "A tutorial on how to generate synthetic instruction datasets in languages other than English."

[taxonomies]
tags = ["Tutorials", "LLM", "multilingual", "magpie", "synthetic data"]
+++

{% admonition(type="tip", icon="tip") %}
Ok, you're finally convinced that synthetic data works... ⚗️

**Now you want to generate an instruction dataset in a language other than English.**

But how do you get started?

I explore how to do this with Magpie [in my new tutorial](https://huggingface.co/blog/anakin87/multilingual-magpie).

For a short intro, read on!
{% end %}

<!-- toc -->

![Generating multilingual instruction datasets with Magpie](multilingual_magpie.jpeg)

## 🐦‍⬛ What is Magpie?

It's a recent technique for creating synthetic instruction datasets.

Magpie is based on a simple but ingenious idea 👇

*If you prompt an instruction-tuned model with a pre-query template, you can make it generate a plausible user instruction.*

Here's an example:
- model: Llama-3-8B-Instruct
- pre-query template: `<|begin_of_text|><|start_header_id|>user<|end_header_id|>`
- generated user instruction: "What are some of the responsibilities of a commercial pilot?"

You can then feed this instruction back into the same model to get the assistant response.

By repeating this process, it's possible to generate large synthetic datasets with relatively little effort.

🪄 The authors demonstrate that using these datasets for Supervised Fine Tuning (SFT) can yield strong performance, even competitive with the original instruct model.

## 🧗 Generating non-English data

Most Language Models are primarily trained on English texts, so they tend to produce data in English.

How can we overcome this?

Earlier approaches were complex or costly.

Then Manuel Romero found a simple solution: add the target language to the pre-query template.
For Spanish, the template becomes `<|begin_of_text|><|start_header_id|>user<|end_header_id|>spanish:`.

This method works for Spanish and German!

❌ Unfortunately, it does not work well for other languages (🇮🇹, 🇳🇱, ...)


## 💡 Magpie with system message

I had another idea: use the system message to steer generation towards a specific language.

The system message should be in the target language, like:
"You are an artificial intelligence that answers users' questions in TARGET_LANGUAGE in a useful and detailed way. The user asks complex questions in TARGET_LANGUAGE."

It is a simple approach, but it might work...

It turns out the authors had a similar idea, which they included in the latest revision of their paper. 🎉

## 🍪 Resources

- [My article - "Generating multilingual instruction datasets with Magpie"](https://huggingface.co/blog/anakin87/multilingual-magpie)

- [Magpie paper and repository](https://arxiv.org/abs/2406.08464) [https://github.com/magpie-align/magpie](https://github.com/magpie-align/magpie)

- [Magpie demo by Daniel van Strien](https://huggingface.co/spaces/davanstrien/magpie)

- [Magpie Ollama Datagen by Manuel Romero](https://github.com/mrm8488/magpie-ollama-datagen)

- [magpie-ultra dataset](https://huggingface.co/datasets/argilla/magpie-ultra-v0.1) - massive dataset built with Magpie by Argilla

- [⚗️ distilabel framework](https://distilabel.argilla.io/latest/) - framework for synthetic data generation and AI feedback at scale
