+++
title = "New Italian Preference Dataset 🇮🇹👍👎"
date = "2025-01-22"
description = "How I improved an existing Italian dataset for DPO."

[taxonomies]
tags = ["LLM", "DPO", "dataset", "Italian", "neogenesis"]
+++

The most common fine-tuning workflow of a Language Models involves two steps:
- *Supervised Fine-Tuning (SFT)*: train the model to follow instructions.
Datasets for this step include instruction-response pairs.

- *Preference Tuning*: align the model with human/AI preferences by training it to favor high-quality responses over poor ones. A simple and effective algorithm to do that is **Direct Preference Optimization (DPO)**.
Data for this step follows this format: instruction, chosen response, rejected response.


During the recent Gemma competition, I trained a nice SFT model and wanted to further improve it with Preference Tuning.

I identified some good datasets (by mii-llm and Ruggero Marino Lazzaroni 🙏) but had limited examples (<3K). 

**Then I found a hidden gem -> 💎 [evol-dpo-ita (by Edoardo Federici)](https://huggingface.co/datasets/efederici/evol-dpo-ita)**

This dataset contains 20K prompts translated from Evol-Instruct, with responses generated using GPT-3.5 Turbo and Claude 3 Opus.

⚠️ It only has a limitation: the response from the stronger model (Claude) is always classified as "chosen" and the other one as "rejected". It is a good but not perfect approximation.


**I thought: I can improve it! 🪄**

I used Llama-3.1-70B-Instruct as a Judge 🧑‍⚖️ to re-rank the responses. 

I queried the model via the cheap Hugging Face API PRO.
My prompt was inspired by the Ultrafeedback prompt (available in distilabel by Argilla).


📊 Results:
- 7% of the times chosen and rejected were swapped 🔀
- Another 7% of responses were ties
- I used the obtained dataset to train 2 models with DPO, achieving significant improvements for Italian! 📈


I've published my new dataset ([anakin87/evol-dpo-ita-reranked](https://huggingface.co/datasets/anakin87/evol-dpo-ita-reranked)) on the 🤗 HF Hub.
📓 **[Code](https://www.kaggle.com/code/anakin87/post-training-gemma-for-italian-and-beyond)**
![Evol DPO ita reranked](https://raw.githubusercontent.com/anakin87/gemma-neogenesis/refs/heads/main/images/evol_dpo_ita_reranked.png)





