# Multilingual Intent Discovery using NLP (Unsupervised Approach)

## 📌 Project Overview

This project focuses on **multilingual intent discovery** from natural language user queries using **Natural Language Processing (NLP)** techniques. Given a large multilingual dataset, the system automatically groups semantically similar queries and infers their underlying intent **without supervised training**.

The project demonstrates a complete NLP pipeline — from raw text preprocessing to semantic representation, clustering, and intent inference — implemented entirely in a Jupyter Notebook.

---

## 🎯 Objectives

- Process and analyze **large-scale multilingual text data**
- Convert natural language queries into **semantic vector representations**
- Discover intent patterns using **unsupervised learning**
- Demonstrate NLP concepts clearly for academic evaluation
- Show sample input–output predictions directly in Jupyter

---

## 🧠 Dataset

- **Dataset**: MASSIVE Multilingual Dataset  
- **Total Samples**: ~842,000  
- **Languages**: 50+ languages (English, Hindi, Tamil, Japanese, Russian, etc.)
- **Fields Used**:
  - `utterance`: user query
  - `intent`: reference intent label (used only for validation)
  - `locale`: language/region code

> The dataset is not included in this repository due to size constraints.

---

## 🔄 NLP Workflow / Pipeline

### 1️⃣ Data Loading
- Multiple `.jsonl` files are merged into a single Pandas DataFrame
- Only relevant fields are retained for NLP processing

### 2️⃣ Text Preprocessing
- Unicode normalization
- Removal of emojis and special characters
- Lowercasing and whitespace normalization

This ensures consistent multilingual text input.

### 3️⃣ Semantic Embedding
- Model used: **`paraphrase-multilingual-MiniLM-L12-v2`**
- Each sentence is converted into a **384-dimensional vector**
- Embeddings are saved to disk (`embeddings.npy`) to avoid recomputation

This step maps semantically similar sentences close together, even across different languages.

### 4️⃣ Unsupervised Clustering
- Algorithm: **MiniBatch KMeans**
- Chosen for:
  - Scalability to large datasets
  - Faster convergence than standard KMeans
- Each cluster represents a discovered intent group

### 5️⃣ Cluster Interpretation
- A representative utterance is selected per cluster
- Ground-truth intent labels are used only for interpretation, not training

### 6️⃣ Inference / Prediction
For a new user query:
1. Text is cleaned
2. Embedded using the same multilingual model
3. Compared to cluster centroids using cosine similarity
4. Closest cluster determines the predicted intent

---

## 🧪 Sample Input & Output

**Input:**
What is the weather in Mumbai today?


**Output:**
Predicted Intent: weather_query
Representative Query: какая погода сейчас в сочи
Language: ru-RU


This demonstrates **cross-lingual semantic understanding**.

---

## 🛠️ Technologies Used

- Python
- Pandas, NumPy
- Sentence Transformers
- Scikit-learn
- MiniBatch KMeans
- Cosine Similarity
- Jupyter Notebook

---

## 📁 Project Structure
multilingual_intent_nlp/
│
├── intent_clustering.ipynb
├── README.md
├── requirements.txt
├── .gitignore
└── results/
└── sample_output.txt



---

## ⚙️ How to Run

1. Install dependencies:
   ```bash
   pip install -r requirements.txt
2. Open the notebook:
jupyter notebook intent_clustering.ipynb
3. Run all cells sequentially
Embeddings load instantly if already saved.

📌 Notes

This is an NLP-focused academic project

No web interface or deployment is included

Demonstration is done via notebook outputs

✅ Conclusion

This project shows how unsupervised NLP techniques can be used to discover and predict intent in large multilingual datasets. By combining semantic embeddings with efficient clustering, the system captures meaningful intent patterns without labeled training data, making it suitable for real-world multilingual applications and academic evaluation.
