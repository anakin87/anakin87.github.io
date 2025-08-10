+++
title = "🦙 Ollama - beyond the surface (unpolished notes)"
date = "2024-01-05"

[taxonomies]
tags = ["LLM", "Ollama", "notes"]
+++

If you are in the LLM game, chances are you've come across Ollama.
These days I am doing a deep dive on it (for something that will be announced soon).

The official project description is "Get up and running with large language models locally".

I'd go a step further: it's akin to **Docker for LLMs**.
- you can quickly run models on different operating systems
- you can package models and templates for reproducible runs (using a Modelfile)


Let's delve a bit deeper 🕵️

- **locally** means your cheap laptop (no GPU for LLM inference), your Mac or even a server located anywhere

- llama.cpp popularized the idea of running LLMs on a standard laptop and introduced the GGUF quantized format, to perform inference on CPU (+GPU if available).
Ollama abstracts away the complexity of installing llama.cpp on different platforms.

    Using GGUF models in Ollama is as simple as typing `ollama run llama2` or `ollama run llama2:7b-text-q5_K_M` (to specify quantization options).

- the goal of Ollama is to easily run LLMs everywhere. In contrast, vLLM and TGI are robust solutions for LLM inference/serving on GPUs.
 Although the goals are quite different, I can see some overlap in the future, if Ollama becomes one of the default ways for running open-source language models.




