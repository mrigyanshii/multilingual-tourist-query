# multilingual-tourist-query
🌍 Multilingual Tourist Query Understanding
NLP + Embeddings + Clustering using the MASSIVE Dataset

The Multilingual Tourist Query Understanding project builds a system capable of understanding and grouping tourist queries from 51 languages.
It uses the MASSIVE dataset, multilingual text cleaning, transformer embeddings, and clustering to discover common tourist intents across languages.

📌 *Project Overview*

Tourists ask similar questions across different languages:

“Where is the nearest metro?”
“¿Dónde está el museo más cercano?”
“सबसे नज़दीकी होटल कहाँ है?”

This project aims to:

1. Convert all multilingual queries into semantic embeddings
2. Cluster them into meaningful intent groups
3. Build the foundation for a multilingual tourist assistant
4. Prepare embeddings for downstream tasks like:
    a. intent classification
    b. search engine for tourist queries
    c. chatbot / API backend

🗂 *Dataset*

This project uses the MASSIVE dataset:
📄 51 languages
📊 842,571 total samples
📝 JSONL file format

Dataset link:
"https://huggingface.co/datasets/amazon/MASSIVE"

⚠️ The dataset is NOT included in this repo because of its large size.
Download it manually and place the JSONL files inside a folder called massive/.

🛠️ *Features*

✔ Load & merge 51 JSONL files
✔ Text normalization & cleaning
✔ Generate 384-dimensional multilingual embeddings
✔ Build semantic clustering of tourist queries
✔ Notebook-based pipeline for reproducibility
✔ Ready for model export + API deployment

📁 *Project Structure*
multilingual-tourist-query-nlp/
│
├── notebook.ipynb                # Full pipeline: loading → cleaning → embeddings → clustering
├── README.md                     # This file
├── requirements.txt              # Project dependencies
├── .gitignore                    # Prevents dataset + models from uploading
│
├── massive/                      # Place MASSIVE dataset here (ignored in Git)
├── models/                       # Saved embeddings & cluster models
└── src/                          # (Optional) backend API code

🔧 *Installation*
1. Clone the repository
git clone https://github.com/<your-username>/multilingual-tourist-query-nlp.git
cd multilingual-tourist-query-nlp

2. Install dependencies
pip install -r requirements.txt

3. Download MASSIVE dataset

Place all .jsonl files into:

multilingual-tourist-query-nlp/massive/

📓 *Running the Notebook*

Open Jupyter:
jupyter notebook

Run the notebook cells in order:

Load dataset
Clean text
Encode with Sentence Transformers
Cluster with KMeans / HDBSCAN
Visualize clusters

🧠 *Model Used*
paraphrase-multilingual-MiniLM-L12-v2

🚀 *Future Work*

Build API using FastAPI
Create a web interface for tourist query search
Train supervised classifier on clustered intents
Deploy model on HuggingFace Spaces

📜 *License*

This project is released under the MIT License.

🙌 *Acknowledgements*

MASSIVE dataset (Amazon Alexa AI)
Sentence Transformers library
HuggingFace Hub
