+++
title = "🧑‍🏫 AutoQuizzer: create a quiz from a URL and play/let the LLM play"
date = "2024-05-16"
description = "Learn how I built this 🔥 application."

[taxonomies]
tags = ["Tutorials", "LLM", "RAG", "Haystack", "demo", "Llama", "Groq"]
+++

<!-- toc -->

## Intro
Do you want to play a game against Llama 3? 🦙🦙🦙


Meet **🧑‍🏫 AutoQuizzer**, a new LLM application that you can use for learning or just for fun.

**Try it out on [🤗 Hugging Face Spaces](https://huggingface.co/spaces/deepset/autoquizzer)**.


## How it works
![AutoQuizzer](https://raw.githubusercontent.com/anakin87/autoquizzer/main/autoquizzer.png)

You provide an URL -> A multiple-choice quiz is instantly generated.

- You can play the quiz yourself.

- You can let the LLM play in two different ways
  - 📕 Closed book: the LLM responds only by knowing the general topic and using its parametric knowledge and reasoning abilities.
  - 🔎🌐 Web RAG: for each question, a Google search is done and the top 3 snippets are included in the prompt for the LLM.


**Stack**
- 🏗️ Haystack LLM framework
- 🦙 Llama 3 8B Instruct
- ⚡ Groq


Original idea: Tuana Çelik

## Resources

- 🎬 Project walkthrough video by Tuana Çelik: {{ youtube(id="C1oJ1ArYYZA") }}
- [👨‍💻 Code](https://github.com/anakin87/autoquizzer)
- [📰 LLMs can write and answer quizzes – but aren't quite ready to disrupt trivia night](https://www.theregister.com/2024/05/29/autoquizzer_llm_quiz_generation/) - The Register