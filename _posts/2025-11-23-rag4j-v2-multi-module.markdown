---
layout: post
title: "RAG4j gets new structure and releases v2"
date: 2025-11-23 10:00:00 +0100
categories: [release]
---
We're excited to announce the release of **RAG4j version 2**! This major update brings a complete refactoring of the project into a modern multi-module setup, making it easier than ever to integrate RAG capabilities into your applications.

## What's new in v2?

The entire RAG4j project has been restructured into a modular architecture. This means you can now include only the parts you need, keeping your dependencies lean and your project focused. Whether you need just the retrieval components, specific embedders, or particular content store integrations, you can pick and choose what fits your use case.

This modular approach also paves the way for new integrations. We're making it simpler to add support for new LLM providers, embedders, and vector stores as the ecosystem continues to evolve.

## Why RAG matters in the age of agents

As AI agents become more prevalent, RAG (Retrieval Augmented Generation) is more important than ever. Agents need access to accurate, up-to-date information to perform their tasks effectively. RAG provides the bridge between Large Language Models and your organization's knowledge base, enabling agents to:

- Access current information beyond their training data
- Ground their responses in factual, retrievable content
- Reduce hallucinations by working with verified sources
- Operate with domain-specific knowledge

## Teaching RAG again

With this renewed focus on RAG's importance, we're reactivating RAG4j as our primary teaching framework. The project was created to make learning RAG accessible, and the new modular structure makes it even better for workshops and education. You can now explore individual components in isolation, making it easier to understand how each piece contributes to the complete RAG system.

The three core parts of our RAG system remain:
- **Retrieval**: Finding relevant chunks from your knowledge base
- **Generation**: Creating answers with context from the retriever
- **Quality**: Measuring and improving your RAG system's performance

## Get started with v2

Ready to try RAG4j v2? Head over to the [RAG4j repository](https://github.com/RAG4J/rag4j) to get started. The new modular structure maintains the same ease of use that made RAG4j popular for learning, while providing the flexibility needed for production applications.

Stay tuned for upcoming workshops and tutorials showcasing the new capabilities!
