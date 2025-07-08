#  Medical Chatbot using LangChain, ChromaDB, and Mistral-7B (.gguf)

This project is a Retrieval-Augmented Generation (RAG) based Medical Chatbot built using:
-  Semantic PDF understanding with `LangChain`
-  Local vector database using `Chroma`
-  Offline Large Language Model: `Mistral-7B-Instruct` in `.gguf` format
-  Biomedical embeddings with `PubMedBERT`
-  Runs entirely **offline** (no OpenAI API)

---

##  Features

-  Ask real medical questions like:
  - *“What are the symptoms of heart disease in women?”*
  - *“How does high blood pressure affect the heart?”*
-  Loads PDF data from Drive and splits intelligently
-  Embeds knowledge with `SentenceTransformer` tuned for medicine
-  Answers generated via a **local Mistral-7B-Instruct** model
-  Private: all inference happens locally — no cloud calls!

---

##  Tech Stack

| Component      | Library / Tool                                 |
|----------------|-------------------------------------------------|
| PDF Loader     | `LangChain`'s `PyPDFDirectoryLoader`            |
| Text Splitter  | `RecursiveCharacterTextSplitter`                |
| Embeddings     | `NeuML/pubmedbert-base-embeddings`              |
| Vectorstore    | `ChromaDB`                                      |
| LLM            | `Mistral-7B-Instruct (.gguf)` via `llama-cpp`   |
| Chain          | `RetrievalQA`                                   |
| Runtime        | Google Colab (CPU)                              |

---
##  Folder Structure
 Medical-Chatbot/
├──  data/
│   └── healthyheart.pdf                # The medical PDF used for chatbot knowledge
│
├──  model/
│   └── mistral-7b-instruct-v0.1.Q4_K_M.gguf  # Quantized LLM in .gguf format (Mistral)
│
├──  notebooks/
│   └── medical_chatbot_colab.ipynb     # Main working notebook
│
├── README.md                           # Project explanation and usage

---

## 🧪 Sample Questions to Try

```text
Who is at risk of heart disease?
What are the symptoms of heart disease in women?
How does high blood pressure affect the heart?
What foods are good for heart health?
How does exercise help reduce heart attack risk?

