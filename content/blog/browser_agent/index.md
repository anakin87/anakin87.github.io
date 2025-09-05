+++
title = "🕵️🌐 Building Browser Agents"
date = "2025-08-13"
description = "Learn how to build an Agent that browses the web like a human"

[taxonomies]
tags = ["Tutorials", "LLM", "Agents", "Haystack", "Gemini", "MCP", "Playwright"]
+++
{% admonition(type="tip", icon="tip") %}
**TL;DR**: I built a Browser Agent from scratch using Haystack, Gemini, and Playwright MCP server 💫

[📓 Notebook](https://haystack.deepset.ai/cookbook/browser_agents)

For a short intro, read on!
{% end %}


<video src="agent.mp4" controls autoplay loop></video>


No API? No problem. Browser Agents can use websites like you do: click, type, wait, read.

🎥 In the video, Agent:
- Goes to Hugging Face Spaces
- Finds FLUX.1 [schnell] space (by Black Forest Labs)
- Expands a short prompt ("my holiday on Lake Como") into a detailed image generation prompt
- Waits for the image
- Returns the image URL


**What else can it do?**

Great for information gathering and summarization

- 🗞️🗞️ Compare news websites and create a table of shared stories with links
- ▶️ Find content creator social profiles from YouTube videos
- 🛍️ Find a product's price range on Amazon
- 🚂 🚌 Gather public transportation travel options...


**How is it built?**

- 🏗️ deepset Hhaystack → Agent execution logic 
- 🧠 Google Gemini 2.5 Flash → Good and fast LLM with a generous free tier
- 🛠️ Microsoft Playwright MCP server → Browser automation tools: navigate, click, type, wait...

Even without vision capabilities, this setup can get quite far.


**Next steps**

- Move from notebook to real deployment
- Try a local open model
- Incorporate vision





