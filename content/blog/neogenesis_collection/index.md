+++
title = "🤏 New Italian Small Language Models: Neogenesis collection"
date = "2025-01-17"
description = "Meet two new Gemma 2 variants with improved Italian performance."

[taxonomies]
tags = ["LLM", "post-training", "Italian", "neogenesis", "Gemma"]
+++


I am happy to release two new language models for the Italian Language!

![models](models.gif)

💪 **[Gemma 2 9B Neogenesis ITA](https://huggingface.co/anakin87/gemma-2-9b-neogenesis-ita)**

Building on the impressive work by VAGO Solutions, I applied Direct Preference Optimization with a mix of Italian and English data.
Using Spectrum, I trained 20% of model layers.

📊 Evaluated on the Open ITA LLM leaderboard, this model achieves strong performance.
To beat it on this benchmark, you'd need a 27B model 😎


🤏 **[Gemma 2 2B Neogenesis ITA](https://huggingface.co/anakin87/gemma-2-2b-neogenesis-ita)**

This smaller variant is fine-tuned from the original Gemma 2 2B it by Google DeepMind.
Through a combination of Supervised Fine-Tuning and Direct Preference Optimization, I trained 25% of the layers using Spectrum.

📈 Compared to the original model, it shows improved Italian proficiency, good for its small size.


Both models were developed during the recent Gemma competition on Kaggle.

🙏 Thanks Samuele Colombo and mii-llm for the help during evaluation.


🤗 [HF collection with all models and datasets](https://huggingface.co/collections/anakin87/gemma-neogenesis-67824b7bf13ac9cfe091fe2e)

📓 [Training code](https://www.kaggle.com/code/anakin87/post-training-gemma-for-italian-and-beyond)





