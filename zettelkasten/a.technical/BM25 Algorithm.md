---
tags:
  - AI
type: permanent
---


How does BM25 Work? 

There are three factors that get put together to make a final numeric score for how relevant a document is to a set of keywords.

1. term frequency: how often keywords appear in the document 
2. IDF (Inverse Document Frequency): Rarity of the keyword across the corpus, rare terms score higher than common terms
3. Length Normalization: adjusts for document length to prevent longer documents from automatically winning.
All of these factors are combined together and get a final score the higher the better 

BM25 limitation:

BM25 is purely keyword-based matching. It can't understand the meaning. If a document mentions "total solar eclipse" but a user searches for "sun blocked by moon", BM25 returns nothing.

 [[embeddings]] can solve this problem by capturing semantic meaning they convert text into vectors (long array of numbers that represent how an llm understand the text) two semantically similar phrases will have similar embeddings, even if they share no keywords.

