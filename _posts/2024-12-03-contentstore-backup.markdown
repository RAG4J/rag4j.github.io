---
layout: post
title:  "Internal content store backup now available in RAG4j"
date:   2024-12-03 05:00:00 +0100
categories: [examples]
---
In the Python version of this project, creating a backup of the _InternalContentStore_ was already possible. With the latest release of RAG4j, you can now also create a backup of the _InternalContentStore_ in Java. You can choose the location of the backup. The backup contains two parts, the data and the metadata. Both use a serialized format. Below are two examples for creating the backup and restoring the backup. 

```java
public class AppRAG {
    public static void main(String[] args) {
        // Setup the content store
        OllamaAccess ollamaAccess = new OllamaAccess();
        Embedder embedder = new OllamaEmbedder(ollamaAccess);
        InternalContentStore contentStore = new InternalContentStore(embedder);

        ContentReader contentReader = new JfallContentReader("jfall/sessions.jsonl");
        IndexingService indexingService = new IndexingService(contentStore);
        Splitter splitter = new SentenceSplitter();
        indexingService.indexDocuments(contentReader, splitter);

        Path backUpPath = Path.of(System.getProperty("user.dir"), "/backups");
        contentStore.backupToDisk(backUpPath, "jfall-ollama-sentence");
    }
}
```

In the next run, you want to restore the backup. You can do this with the following code:

```java
public class AppRAG {
    public static void main(String[] args) {
        // Setup the content store
        OllamaAccess ollamaAccess = new OllamaAccess();
        Embedder embedder = new OllamaEmbedder(ollamaAccess);
        InternalContentStore contentStore = new InternalContentStore(embedder);
        
        Path backUpPath = Path.of(System.getProperty("user.dir"), "/backups");
        contentStore.loadFromDisk(backUpPath, "jfall-ollama-sentence");
    }
}
```
Not having to create the chunks and embeddings is the biggest advantage of using the backup.