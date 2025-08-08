
# 🏥 Generative AI for Healthcare: MIMIC-IV QA System

This project implements a pipeline for developing and fine-tuning LLM-based question answering systems on structured and unstructured healthcare datasets, specifically from MIMIC-III and MIMIC-IV.

## 📂 Components

### 1. `cleaned_MIMIC_QA.ipynb`
- Merges and preprocesses MIMIC-III and IV QA CSV files
- Aligns ICD codes and clinical notes with diagnosis records
- Outputs structured inputs for downstream fine-tuning

### 2. `cleaned_MIMIC_IV.ipynb`
- Processes MIMIC-IV EHR records for LLM consumption
- Prepares patient demographics, vitals, labs, and diagnoses
- Structures tokenized input for QA tasks

### 3. `cleaned_base_model.ipynb`
- Loads a pre-trained LLM (OpenAI or Hugging Face)
- Performs inference on QA samples before fine-tuning
- Evaluates baseline performance using accuracy and BLEU

### 4. `cleaned_fine_tuned_model.ipynb`
- Fine-tunes the base model on domain-specific QA pairs
- Evaluates improvements in performance post-training
- Includes support for metrics like ROUGE, BERTScore

## 🧠 Techniques Used

- Retrieval-Augmented Generation (RAG)
- Fine-tuning transformer models
- QA evaluation using BERTScore, BLEU, ROUGE
- Data preprocessing from MIMIC-IV and MIMIC-III

## 🔐 API Key Handling

Any hardcoded API keys have been removed. Use environment variables:

```python
import os
openai.api_key = os.getenv("OPENAI_API_KEY")
```

Set your key in your environment:

```bash
export OPENAI_API_KEY="your-key"     # macOS/Linux
set OPENAI_API_KEY="your-key"        # Windows CMD
```

## 🚀 Getting Started

1. Install required libraries:

```bash
pip install openai pandas datasets scikit-learn transformers evaluate
```

2. Set environment variables for OpenAI or Hugging Face access
3. Open and run each notebook in the provided order

## 📌 License

This project is for academic and research use only. Be sure to follow the licensing terms of MIMIC-IV and any external APIs used.
