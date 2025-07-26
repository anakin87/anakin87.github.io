+++
title = "📝 GRPO: what I've learned"
date = "2025-05-15"

[taxonomies]
tags = ["GRPO", "LLM", "fine-tuning", "post-training", "Reinforcement Learning"]

+++

<!-- toc -->

[I recently experimented with GRPO](../qwen-scheduler-grpo) and I want to share what I've learned.



## 𝗚𝗥𝗣𝗢 𝗶𝘀 𝗴𝗿𝗲𝗮𝘁 𝗳𝗼𝗿 𝘃𝗲𝗿𝗶𝗳𝗶𝗮𝗯𝗹𝗲 𝘁𝗮𝘀𝗸𝘀

![GRPO](raschka_grpo.jpeg)

It simplifies the typical Reinforcement Learning setup (used, for example, in PPO): 

✅ No value model

✅ Reward model often replaced by deterministic reward functions (Reinforcement Learning with Verifiable Rewards).

Since only prompts are required for your dataset (no completions), data collection becomes much easier and cheaper than in Supervised Fine-Tuning.

For a solid introduction, read the [✍️ recent article by Sebastian Raschka, PhD](https://sebastianraschka.com/blog/2025/the-state-of-reinforcement-learning-for-llm-reasoning.html). Image credit: same author.

## 𝗪𝗵𝗲𝗻 𝘁𝗼 𝘂𝘀𝗲 𝗚𝗥𝗣𝗢?

Use GRPO if:
- You can clearly explain the task to the model in a prompt.
- You can figure out how to reward good outputs.
- You can sometimes identify encouraging behaviors in the model to train.

## 𝗘𝗹𝗶𝗰𝗶𝘁𝗮𝘁𝗶𝗼𝗻

Using GRPO and similar algorithms is more about eliciting desired behaviors from the trained model than teaching completely new stuff to it. 

If you need fundamentally new skills, Supervised Fine-Tuning (and distillation) might be more effective .

([📖 Does Reinforcement Learning Really Incentivize Reasoning Capacity in LLMs Beyond the Base Model?](https://arxiv.org/abs/2504.13837)). 

If you are curious about these topics, follow Nathan Lambert and the [✍️ Interconnects AI blog](https://www.interconnects.ai/).

## 𝗕𝗮𝘀𝗲 𝗺𝗼𝗱𝗲𝗹 𝗺𝗮𝘁𝘁𝗲𝗿𝘀

If the base model never shows promising behaviors on the task during sampling, GRPO likely won't help.
You probably need a bigger or better base model first.

## 𝗥𝗲𝘄𝗮𝗿𝗱 𝗳𝘂𝗻𝗰𝘁𝗶𝗼𝗻𝘀 𝗱𝗲𝘀𝗶𝗴𝗻 𝗶𝘀 𝗰𝗿𝘂𝗰𝗶𝗮𝗹

Your rewards should capture your goal, provide a learnable signal (an encouragement to the model), and be robust. 

If they are not robust, you may experiment reward hacking: the model finds shortcuts to maximize the reward without 
actually solving the problem you had in mind. Nice and frustrating 😅

## "𝗔𝗵𝗮 𝗺𝗼𝗺𝗲𝗻𝘁" 𝗺𝗶𝗴𝗵𝘁 𝗯𝗲 𝗼𝘃𝗲𝗿-𝗵𝘆𝗽𝗲𝗱

In the DeepSeek-R1 paper, the authors showed that during GRPO "the model learns to rethink using an anthropomorphic tone".

A miracle? Recent studies have cast some doubt on this. ([📖 There May Not be Aha Moment in R1-Zero-like Training](https://oatllm.notion.site/oat-zero); [📖 Understanding R1-Zero-Like Training: A Critical Perspective](https://arxiv.org/abs/2503.20783))

They found that similar "aha moments" could be found in the base models before any GRPO training even started.

## 𝗨𝗻𝘀𝗹𝗼𝘁𝗵: 𝗴𝗿𝗲𝗮𝘁 𝗳𝗼𝗿 𝘀𝗮𝘃𝗶𝗻𝗴 𝗚𝗣𝗨, 𝗯𝘂𝘁 𝗯𝗲𝘄𝗮𝗿𝗲

Unsloth is one of the most popular libraries for fine-tuning Language Models, especially if you don't have much GPU.

These guys do impressive things in terms of GPU efficiency. 
However, it currently patches many other libraries and comes with some tricky bugs. 🐛

If you have enough VRAM, TRL is more stable.





