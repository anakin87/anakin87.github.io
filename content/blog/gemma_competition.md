+++
title = "💎🌍🇮🇹 Gemma Neogenesis - Improving Gemma 2 for a Specific Language on a Budget: Post-Training Recipe"
date = "2025-01-15"
description = "My submission to the Kaggle Gemma competition."

[taxonomies]
tags = ["Tutorials", "LLM", "post-training", "neogenesis", "Italian", "TRL", "Gemma"]
+++

{% admonition(type="tip", icon="tip") %}
👨‍💻 You can find the code on **[this Kaggle notebook](https://www.kaggle.com/code/anakin87/post-training-gemma-for-italian-and-beyond)**.
{% end %}

Hey, it has been a while... I was busy participating in [💎 Gemma competition](https://www.kaggle.com/competitions/gemma-language-tuning)!

So, what's this Kaggle competition about?

Gemma open models have a large vocabulary size (256K), so improving them for a specific language or cultural context should be pretty affordable - no need for continued pre-training.


My submission: [💎🌍🇮🇹 Neogenesis - Post-Training Gemma for Italian and beyond](https://www.kaggle.com/code/anakin87/post-training-gemma-for-italian-and-beyond)

In my notebook, I show how I improve the performance of Gemma 2 2B on Italian via Post-Training.
I believe this method is adaptable to other languages and model sizes.

*Key steps:*

📊 Choose reference metrics

🧑‍🔬 Data curation for Instruction Fine Tuning: identify existing datasets + generate synthetic data

🏋️‍♂️ Efficient Instruction Fine Tuning with Spectrum

🧑‍🔬 Data curation for Preference Tuning: identify existing datasets + generate synthetic data

👍👎 Efficient Direct Preference Optimization with Spectrum

📈 Evaluation


Check out the full details in the [📓 notebook](https://www.kaggle.com/code/anakin87/post-training-gemma-for-italian-and-beyond).

![Gemma Neogenesis](https://github.com/anakin87/gemma-neogenesis/blob/main/images/neogenesis.jpg?raw=true)




