+++
title = "👑 🗓️ I trained a Language Model to schedule events with GRPO!"
date = "2025-04-29"
description = "An experiment on using GRPO on a new task + all what I learned"

[taxonomies]
tags = ["Tutorials", "GRPO", "LLM", "fine-tuning", "post-training", "Reinforcement Learning"]
+++

{% admonition(type="tip", icon="tip") %}
I've published an [extensive post on this topic on the 🤗 Hugging Face blog](https://huggingface.co/blog/anakin87/qwen-scheduler-grpo).

All code is available on [GitHub](https://github.com/anakin87/qwen-scheduler-grpo).

For a short intro, read on!

{% end %}


<!-- toc -->

![Qwen Scheduler GRPO](qwen_scheduler_grpo.gif)

I experimented with GRPO lately.

I am fascinated by models learning from prompts and rewards - no example answers needed like in Supervised Fine-Tuning.

After the DeepSeek boom, everyone is trying GRPO with GSM8K or the Countdown Game...

I wanted a different challenge, like teaching a model to create a schedule from a list of events and priorities.

Choosing an original problem forced me to:

🤔 Think about the problem setting

🧬 Generate data 

🤏 Choose the right base model

🏆 Design reward functions (and experiencing reward hacking) 

🔄 Run multiple rounds of training, hoping that my model would learn something.

A fun and rewarding 😄 experience.

I learned a lot of things, that I want to share with you.

- ✍️ [Blog post](https://huggingface.co/blog/anakin87/qwen-scheduler-grpo)
- 💻 [Code](https://github.com/anakin87/qwen-scheduler-grpo)
- 🤗 [Hugging Face collection](https://huggingface.co/collections/anakin87/qwen-scheduler-grpo-680bcc583e817390525a8837)





