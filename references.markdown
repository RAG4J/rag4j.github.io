---
layout: page
title: References
permalink: /references/
---

## OpenAI
<img src="/assets/images/openai.png" alt="OpenAI Logo" style="height: 100px; padding: 50px;">

I don't think that OpenAI needs an introduction if you reached this page. If you are not familiar with OpenAI, you can find more information on their [website](https://openai.com). We use OpenAI in this project for multiple tasks. We use OpenAI to create embeddings, to generate answers, to generate questions, and te verify the quality of given answers.

## Ollama
<img src="/assets/images/ollama.png" alt="Ollama Logo" style="height: 100px; padding: 50px;">

You use Ollama to run different Large Language Models on your local machine. Downloads are available for Windows, MacOS, and Linux. You can find more information on their [website](https://ollama.com). Both Rag4j and Rag4p have good integrations with Ollama.

## Weaviate
<img src="/assets/images/weaviate.png" alt="Weaviate Logo" style="height: 100px; padding: 50px;">

In this project we use an InternalContentStore. This is handy when working with just a few vectors. It does not persist the data. Therefore you need to index the content on every run. With Weaviate we have vector store with a lot more capabilities. At the moment we just scratch the service of the power of Weaviate. We will implement Hybrid search and probably some more advanced features later on. If you want more information about Weaviate, you can find it on their [website](https://weaviate.io).

