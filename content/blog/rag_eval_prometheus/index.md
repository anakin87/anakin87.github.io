+++
title = "🧪 RAG Evaluation with 🔥 Prometheus 2"
date = "2024-06-17"
description = "Learn how to evaluate RAG pipelines with an open model"

[taxonomies]
tags = ["Tutorials", "LLM", "evaluation", "Haystack", "RAG", "Prometheus"]
+++

![Prometheus 2](prometheus.png)

When evaluating LLMs' responses, **proprietary models** like GPT-4 are commonly used due to their strong performance.

However, relying on closed models presents challenges related to data privacy 🔒, transparency, controllability, and cost 💸.

On the other hand, **open models** typically do not correlate well with human judgments and lack flexibility.


🔥 [Prometheus 2](https://arxiv.org/abs/2405.01535) (by KAIST AI) is a new family of open-source models designed to address these gaps:
- two variants ([7B](https://huggingface.co/prometheus-eval/prometheus-7b-v2.0) and [8x7B](https://huggingface.co/prometheus-eval/prometheus-8x7b-v2.0))
- trained on open-source data
- high correlation with human evaluations and proprietary models
- highly flexible: capable of performing direct assessments and pairwise rankings, and allowing the definition of custom evaluation criteria.


I experimented with Prometheus 2 + Haystack to evaluate RAG across different dimensions.
- [📝 Blog post](https://haystack.deepset.ai/blog/rag-evaluation-with-prometheus-2)
- [📓 Notebook](https://haystack.deepset.ai/cookbook/prometheus2_evaluation)
