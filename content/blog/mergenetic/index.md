+++
title = "🧪 Mergenetic: evolutionary model merging for all"
date = "2025-07-29"
description = "Intro to a recent libray/papers on evolutionary model merging"

[taxonomies]
tags = ["LLM", "model merging", "paper"]
+++


<!-- toc -->

![Mergenetic](mergenetic.gif)



## Model merging basics
The idea of model merging is pretty simple
- take 2 or more models with different capabilities (let's say 🇯🇵 Japanese and 🧮 Math) fine-tuned from the same base model
- combine their weights using interpolation (SLERP) or other techniques
- get a merged model with both capabilities (🇯🇵🧮)

This approach is effective and works on consumer hardware (no GPU needed).

In 2024, model merging got popular, thanks to the Mergekit library (Charles Goddard/Arcee AI). Maxime Labonne has released several impressive models and contributed to popularize this paradigm.

## Evolutionary Model Merging

Despite this success, choosing the models to merge, the techniques and their parameters is a form of black art, relying on intuition and trial and error. 🔮

To fix this, Sakana AI introduced 🧬 **Evolutionary Model Merge**, a general method using evolutionary algorithms to discover optimal ways to combine open models.

Evolutionary Algorithms are black-box optimization algorithms operating on a population of potential solutions by evolving them through generations with operators such as selection, mutation, recombination, and crossover. The fitness function is crucial, as it evaluates the quality of each solution, guiding the selection process by favoring higher-scoring solutions for reproduction.

Among the models Sakana AI released to demonstrate this technique is EvoLLM-JP, an LLM with Japanese and math capabilities, resulting from merging multiple models.


💸 Evolutionary Model Merging has one major problem: repeatedly evaluating the fitness function on candidate models is expensive. It requires these models to generate completions on a held-out validation set.

Reproducing EvoLLM-JP's evolutionary merging with an NVIDIA 4090 (24GB VRAM) would take 2 months 🤯

## MERGE3 and Mergenetic: evolutionary model merging for all

🪄 The researchers of GLADIA first invented a technique called MERGE3 that extracts a reduced dataset for evaluation, estimates model abilities using Item Response Theory (IRT), and evolves optimal merges via IRT-based performance estimators.

**MERGE3** achieves similar results to EvoLLM-JP, while reducing fitness computation costs 50×.
Evolving such a model can require hours instead of months!


GLADIA researchers are now releasing 🧪 **Mergenetic**, a library for Evolutionary Model Merging
- ⭐ User friendly and research oriented
- ⭐ Rich in merging techniques and evolutionary algorithms
- ⭐ Multi-objective optimization
- ⭐ Accelerated evolution through subsampling and approximation (with techniques like MERGE3)
- ⭐ integrates with LM Eval Harness and supports custom fitness functions
- ⭐ offers a Python API, a CLI and a GUI

I recommend giving it a try to evolve your models affordably.

👥 Authors: Adrian Robert Minut, Tommaso Mencattini, Andrea Santilli, Donato Crisostomi, Emanuele Rodolà



## 📚 Resources

- [Mergenetic library](https://github.com/tommasomncttn/mergenetic)
- [Mergenetic paper](https://arxiv.org/abs/2505.11427)
- [MERGE3 paper](https://arxiv.org/abs/2502.10436)

Sakana AI - Evolutionary Model Merging
- [Paper](https://www.nature.com/articles/s42256-024-00975-8)
- [Blog post](https://sakana.ai/evolutionary-model-merge/)




