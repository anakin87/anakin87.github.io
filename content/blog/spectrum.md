+++
title = "🎯 Selective fine-tuning of Language Models with Spectrum"
date = "2025-02-04"
description = "An introduction to Spectrum, a method for selection of model parameters for efficient training."

[taxonomies]
tags = ["Tutorials", "Spectrum", "QLoRA", "LLM", "fine-tuning", "paper"]
+++

{% admonition(type="tip", icon="tip") %}
I've published an [extensive tutorial on Spectrum on the 🤗 Hugging Face blog](https://huggingface.co/blog/anakin87/spectrum).
For a short intro, read on!
{% end %}


<!-- toc -->


## QLoRA
QLoRA revolutionized LLM fine-tuning in May 2023.

This method trains Low Rank Adapters on top of a quantized Language Model, drastically reducing GPU memory usage.

QLoRA made fine-tuning accessible on consumer hardware and became incredibly popular.


However, **QLoRA has some limitations** ⛔
- Lower performance compared to full fine-tuning.
- Highly sensitive to hyperparameters (rank and alpha).
- LoRA-trained models introduce "intruder" dimensions, potentially misaligning them with pre-training distribution and limiting adaptability to new tasks (see [LoRA vs Full Fine-tuning: An Illusion of Equivalence](https://arxiv.org/abs/2410.21228)).


Looking for simplicity, full performance, and memory savings?

## Spectrum
🎯 **Spectrum** is an interesting alternative.

![Spectrum diagram](https://github.com/anakin87/gemma-neogenesis/blob/main/images/spectrum_diagram.png?raw=true)

🔬 Analyzes weight matrices for all layers in a Language Model and calculates a Signal to Noise Ratio (SNR) for each one.

🔹 Uses Random Matrix Theory (Marchenko-Pastur distribution) to distinguish signal from noise.

🔹 Based on a chosen percentage (say, 25%), Spectrum selects the most informative layers of each type (e.g., mlp.down_proj, self_attn.o_proj, etc.).

🔹 You can then ❄️ freeze the entire model except for these selected layers 🔥 and focus your fine-tuning on them.


### Spectrum: evaluation and results

In the paper, the authors fine-tuned Llama-3-8B and Mistral-7B-v0.1 on the airoboros-3.1 dataset using Spectrum-50 and Spectrum-25, comparing results with full fine-tuning and QLoRA.

📊 Spectrum is competitive with full fine-tuning and outperforms QLoRA on benchmark performance.

⚡ More memory-efficient than QLoRA in distributed training. QLoRA uses less memory on a single GPU.

Several impressive Language Models have been trained using Spectrum, including Dolphin models, Llama 3.1 Storm, numerous models by VAGO Solutions...

💎 Spectrum helps mitigate catastrophic forgetting—as Fernando (one of the authors) puts it:
"Training the layers with highest SNR implies training matrices with lower compression ratio. These are more prone to learn something new without forgetting. Learn more, forget less."


### 🙋‍♂️ My experience with Spectrum
Since my first experiments with this method, I've found it both effective and enjoyable to work with—I quickly became a fan.
I used it to create Italian versions of Phi 3.5 Mini and Gemma 2.

Spectrum is usable out of the box with the Axolotl fine-tuning framework,
but with a small effort, you can make it work with Hugging Face TRL.

🙏 Great work by Eric Hartford, Lucas Atkins, Fernando Fernandes Neto, and David Golchinfar (Arcee AI + VAGO Solutions)!

## 📚 Resources
- [Spectrum tutorial](https://huggingface.co/blog/anakin87/spectrum)
- [Post-Training Gemma for Italian and beyond](https://www.kaggle.com/code/anakin87/post-training-gemma-for-italian-and-beyond) (makes extensive use of Spectrum)
- [Spectrum paper](https://arxiv.org/abs/2406.06623)
- [Spectrum code](https://github.com/cognitivecomputations/spectrum)