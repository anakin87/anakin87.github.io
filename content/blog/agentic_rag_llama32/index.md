+++
title = "🕵🏻 Agentic RAG with 🦙 Llama 3.2 3B"
date = "2024-09-26"
description = "Combine RAG on a knowledge base with Web Search to intelligently answer user questions."

[taxonomies]
tags = ["Tutorials", "LLM", "RAG", "Agents", "Llama", "Haystack"]
+++

![Agentic RAG with Llama 3.2 3B](agentic_rag_llama.jpeg)

I was excited to explore Llama 3.2, but as a simple 🇪🇺 EU guy, I don't have access to Meta's multimodal models. 😿

🤔 So I thought: why not challenge the small 3B text model with Agentic RAG?

🎯 The plan:
- Build a system that tries to answer questions using a knowledge base.
- If the documents don't contain the answer, use Web search for additional context.


**Check out my [experimental notebook](https://haystack.deepset.ai/cookbook/llama32_agentic_rag)**


My stack:
- 🏗️ Haystack: open-source LLM orchestration framework
- 🦙 Llama-3.2-3B-Instruct
- 🦆🌐 free DuckDuckGo API, integrated with Haystack - huge thanks to Giovanni Alzetta!

✨ *The results? Encouraging - a few months ago, this level of performance from a small model would have been unthinkable.*

This probably reflects the impressive IFEval score of the model (comparable to Llama 3.1 8B).