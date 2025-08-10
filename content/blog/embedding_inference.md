+++
title = "🧭 Choosing an embedding inference solution for open models"
date = "2024-03-10"
description = "Notes on the landscape of embedding inference solutions/libraries for open models"

[taxonomies]
tags = ["embeddings", "inference", "notes"]
+++

<!-- toc -->

These days we have many good open embedding models - think for example of the models released by Mixedbread a few days ago.

There are also several libraries to use/serve them.
Navigating this landscape can be complex, so let's explore together (thanks to Luca Santuari for the question). 👇

## ⭐ Sentence Transformers
A cornerstone library for computing text embeddings. Most of the embedding models available on Hugging Face are compatible with it.

Originally developed by Ubiquitous Knowledge Processing (UKP) Lab and Nils Reimers, it was recently revamped by HuggingFace and is maintained by Tom Aarsen. 💙

Python library, depends on PyTorch, may not be the most efficient and fast. Runs best on GPU. 

**2025 Update**: Sentence Transformers now also offers ONNX and OpenVINO support, for speeding up inference on different hardware.




## 🚀 HF Text Embeddings Inference
Toolkit for deploying and serving open-source text embedding models.

Very fast and efficient: based on the Rust candle framework. Runs via docker and supports both CPU and GPU.

Compatible with several Sentence Transformers model architectures.

Not fully liberal open source license.

**2025 Update**: Switched to Apache 2.0 license. 🎉



## 🤗 HF Optimum
This project is an extension of Transformers that provides a set of performance optimization tools to train and run models with maximum efficiency.

It supports different specialized hardware options from various vendors (Nvidia, Intel...) and the cross-platform ONNX runtime.

This toolkit can also be used to compute embeddings with different and efficient CPU and GPU options.




## ⚡️ FastEmbed
Originally developed by Nirant Kasliwal and maintained by Qdrant, this library provides fast and efficient embedding generation. Easy to use.
It is based on the ONNX runtime and runs on CPU and GPU. Supports a limited but growing selection of models.


## 🦙 Ollama
Very popular library for LLM serving on standard machines, using the GGUF quantized format.
Recently improved support for embedding models. It uses CPU and GPU if available.
The embedding functionality is still immature compared to previous solutions, but it might make sense if you already use it for Generative Language Models.


You know what? 😉 All of these solutions are supported by the Haystack LLM framework 👉 https://docs.haystack.deepset.ai/docs/embedders


A special mention goes to ♾️ Infinity, by Michael Feil, which I have not tried yet, but looks great!





