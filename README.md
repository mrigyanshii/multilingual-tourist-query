# Multilingual Intent Discovery using NLP

This project demonstrates an NLP-based system for discovering user intent from multilingual queries using **semantic sentence embeddings** and **unsupervised clustering**.

## Dataset
- MASSIVE Multilingual Dataset
- Supports multiple languages (EN, HI, TA, JA, RU, etc.)

## Pipeline
1. Load multilingual utterances
2. Text preprocessing & normalization
3. Sentence embeddings using `paraphrase-multilingual-MiniLM`
4. Scalable clustering with MiniBatchKMeans
5. Semantic intent prediction using cosine similarity

## Example
**Input:**

