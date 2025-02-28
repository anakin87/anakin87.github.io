+++
title = "🈯🦙 Translate instruction datasets using a LLM + LLM as a Judge 🧑‍⚖️"
date = "2025-01-20"
description = "A cheap recipe to translate instruction datasets and ensure data quality."

[taxonomies]
tags = ["Tutorials", "LLM", "fine-tuning", "dataset", "Italian", "neogenesis"]
+++

{% admonition(type="tip", icon="tip") %}
💻 You can find the code on **[this Kaggle notebook](https://www.kaggle.com/code/anakin87/post-training-gemma-for-italian-and-beyond)**.
For a short intro, read on!
{% end %}

<!-- toc -->

## Motivation

If you want to fine-tune a Language Model in a specific language, you usually need an instruction dataset (prompt + response) in your target language.

❌ Good instruction datasets in your target language may not be available.

💡 Translate an English dataset into your target language.

This common approach is not perfect, but using LLM as a Judge can improve quality

Here's how I approached this for the recent Gemma competition. 👇

## Recipe

I wanted to improve Gemma for Italian 🇮🇹.
I already identified the [capybara-claude-15k-ita dataset](https://huggingface.co/datasets/efederici/capybara-claude-15k-ita) (by Edoardo Federici): good but relatively small.

So, I did the following:

![Recipe](https://raw.githubusercontent.com/anakin87/gemma-neogenesis/refs/heads/main/images/llm_aided_translation_diagram.png)

0. Start with a strong base dataset  
I started from [FineTome-100k](https://huggingface.co/datasets/mlabonne/FineTome-100k) (by Maxime Labonne), a subset of [The-Tome (Arcee AI)](https://huggingface.co/datasets/arcee-ai/The-Tome), filtered to include examples with high educational value. Contains quality conversations, reasoning problems, ...

1. Extract single-turn conversations and deduplicate  
To minimize API calls for translation, I focused on single-turn conversations (the other dataset includes multi-turn examples).
For deduplication, I used MinHash (implementation from distilabel by Argilla).

2. Translate the instructions  
For this step, you need a LLM proficient in your target language.
I used Llama-3.1-70B-Instruct via Hugging Face API.

3. Evaluate the translated instructions using a LLM as a Judge 🧑‍⚖️  
Same model and same API.
LLM as a Judge is simple: we ask the LLM to evaluate both the quality of the instruction and its Italian fluency.

4. Remove low-quality instructions

5. Evaluate the Italian correctness and fluency

6. Evaluate the translated responses using a LLM as a Judge 🧑‍⚖️  
I evaluated the Italian correctness and how well the response aligned with the instruction.
The prompt is inspired by the Ultrafeedback prompt (available in distilabel).

7. Remove low-quality responses

With my final dataset [🍷🇮🇹 fine-instructions-ita-70k](https://huggingface.co/datasets/anakin87/fine-instructions-ita-70k), Gemma's Italian performance improved. 🥳

💻 [**Code**](https://www.kaggle.com/code/anakin87/post-training-gemma-for-italian-and-beyond)


## 🤏 Costs and model provider
Hugging Face PRO gives you 20K daily requests for just $9/month!

If you are patient and on a budget, this is a great solution 🤩

Thanks to Maziyar PANAHI for this suggestion!


## ⚠️ Caveats
- While LLM as a Judge helps remove bad translations and low-quality instructions and responses cheaply, it is not perfect. 
- Translating English datasets can result in fluent and correct text in your target language, but lacking cultural nuances and idiomatic expressions.





