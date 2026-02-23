---
tags:
  - AI
type: permanent
---
Embeddings solve this problem by capturing semantic meaning. They convert text into vectors - long arrays of numbers that represent how an LLM understands the text. Two semantically similar phrases will have similar embeddings, even if they share no keywords.

To search with embeddings, we compare one embedding to another using [cosine similarity](https://ai-sdk.dev/docs/reference/ai-sdk-core/cosine-similarity). This mathematical function tells us how close two embeddings are in vector space, giving us a score that represents how similar the search text is to each document.