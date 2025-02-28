+++
title = "🦙📱 Running Small Language Models on a cheap smartphone"
date = "2024-04-09"

[taxonomies]
tags = ["LLM", "Quantization", "Gemma"]
+++

<video src="gemma-2b-orpo-phone.mp4" controls autoplay loop></video>

You may have noticed that this is not Groq 😉

It's my recent small language model running on the CPU of my cheap Nokia X10 phone.


After quantizing [gemma-2b-orpo with the GGUF format](../gemma_2b_orpo_quantization/),
I got eager to get it running on my phone
and I found several ways 👇


🥱 **Lazy way**
- download Layla Lite app (free APK) from their [website](https://www.layla-network.ai/)
- download a GGUF model
- from the app settings, choose your local model and an appropriate Chat template (ChatML in my case)
- put your phone in airplane mode ✈️
- you are ready to chat!


There is also a 🧑‍💻 **hardcore way**, that involves using Termux and compiling Llama.cpp on the phone 👇

[reddit/LocalLLaMA thread](https://www.reddit.com/r/LocalLLaMA/comments/14rncnb/local_llama_on_android_phone/)


🔮 This was a fun experiment that gives an idea of what we might see in the future.


