+++
title = "📝 Fine-tuning LLMs: what I've learned"
date = "2024-08-26"
description = "Lessons learned from my fine-tuning failures 😊."

[taxonomies]
tags = ["LLM", "post-training", "Fine-tuning", "notes"]
+++

<!-- toc -->
## 0️⃣ Familiarize with the jargon
SFT, PPO, DPO, QLoRA... 🤯

For a simple and visual overview, I recommend a recent [post by Leonie Monigatti](https://www.linkedin.com/posts/804250ab_llm-fine-tuning-activity-7229073338042593280-i_1R).

## 1️⃣ Not all models are made equal
Besides performance, some models from big labs are easier to fine-tune than others.

You can get a sense of this by looking at how many fine-tunes a specific model has on HF Hub.

For example, there are many fine-tunes of Llama and Mistral models; Phi-3-small, despite strong on benchmarks, has a very custom architecture that makes it tough to fine-tune.

## 2️⃣ Data 🗃️
Good, relevant data matters. If you are fine-tuning on creative writing examples, don't expect improvements on general knowledge/reasoning benchmarks.

Despite some skepticism, synthetic data is a thing. Don't trust me: read the recent technical reports on Llama3.1 and Gemma2.
Then check out [⚗️ distilabel by Argilla](https://github.com/argilla-io/distilabel).

## 3️⃣ Data preparation
- Ensure you’re correctly applying the chat template to your examples (if needed).
- Fine-tuning libraries like HF TRL (Aloxotl, Unsloth AI...) expose parameters like `max_seq_length` (for SFT), `max_prompt_length` and `max_length` (for DPO). Using default values might truncate your examples, which can be fine, but it's better to be aware. For more details, check out [a great article by Philipp Schmid](https://www.philschmid.de/dpo-align-llms-in-2024-with-trl).

## 4️⃣ No space left on device 🛑
This is silly but real. Make sure you have enough storage space before starting fine-tuning. Also, configure your training to save a manageable number of checkpoints.

## 5️⃣ Evaluation and benchmarks ⚖️
Take some time to understand how these work.

For example, [lm-evaluation-harness by EleutherAI](https://github.com/EleutherAI/lm-evaluation-harness) is the evaluation framework that powers the HF Open LLM Leaderboard, standardizing many tasks.

Something I didn't know: for multiple-choice benchmarks (like MMLU), the framework scores an example using the (log) probability of each option instead of the full-text response. 
To dig deeper into LLM benchmarks, I recommend [the interview with Clémentine Fourrier (maintainer of Open LLM Leaderboard) on the Latent Space podcast](https://www.latent.space/p/benchmarks-201).

## 6️⃣ Need a GPU?
Take a look at [PrimeIntellect compute](https://www.primeintellect.ai/): a new product, that acts as a GPU marketplace. It's not fully refined yet, but it's easy to use and promising.

I'm not sponsored by them, but hey, if they want to give me some free GPUs, I won't complain :-)





