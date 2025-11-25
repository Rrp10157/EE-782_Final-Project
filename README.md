# Legal Machine Translation (English → Hindi)
### Fine-tuning OPUS-MT and NLLB-200 for Indian Judicial Texts  
**EE782: Natural Language Processing – Final Project, IIT Bombay**

---

## 📌 Overview
This repository contains all code, datasets, model outputs, and analysis for our project:

**“Legal Machine Translation for Indian Judicial Texts:  
A Comparative Study of OPUS-MT and NLLB-200 for English–Hindi Translation.”**

We fine-tuned two neural machine translation models:

1. **OPUS-MT (Helsinki NLP)** – lightweight bilingual Transformer  
2. **NLLB-200 (Distilled 600M)** – large multilingual Transformer from Meta

Both models were trained and evaluated on **Indian legal-domain parallel data**, including court judgments and legal proceedings.

---
---

## 🚀 Models Used

### **1. OPUS-MT (Helsinki-NLP/opus-mt-en-hi)**
- ~90M parameter bilingual Transformer  
- Trained originally on OPUS corpus  
- Lightweight & fast  
- Serves as a **baseline**

### **2. NLLB-200 Distilled 600M (facebook/nllb-200-distilled-600M)**
- 600M parameter multilingual model  
- Trained across 200+ languages  
- Strong zero-shot & fine-tuned performance  
- Achieved highest legal MT accuracy in our experiments  

---

## 📊 Dataset

We use a curated English–Hindi legal dataset:

| Split         | Size      | Purpose                 |
|---------------|-----------|--------------------------|
| Train         | 17,500    | Model fine-tuning        |
| Validation    | 7,500     | Metric-based evaluation  |
| Test          | 5,000     | Final performance        |

All text samples are judicial sentences, covering:
- High Court & Supreme Court case orders  
- Affidavits  
- Statutory language  
- Legal arguments & procedural text  

---

## ⚙️ Installation

Install required dependencies:

setup:
  install_commands:
  
    - pip install transformers datasets sentencepiece sacrebleu evaluate accelerate rouge-score

training_instructions:
  opus_mt:
    notebook: notebooks/EE782_FinalProject_Opus.ipynb
    environment: "Google Colab (T4 GPU recommended)"
    steps:
      - Tokenization
      - Preprocessing
      - "Fine-tuning for 1000 steps"
      - "Validation: BLEU, ROUGE-L, ChrF"
      - Test set inference
      - Plot generation

  nllb_200:
    notebook: notebooks/EE782_FinalProject_NLLB_final_submission.ipynb
    details:
      - "Loads multilingual tokenizer (eng_Latn / hin_Deva)"
      - "Enables gradient checkpointing for Colab GPU"
      - "Fine-tunes for up to 1000 steps"
      - "Generates output CSV and performance metrics"
      - Logs training curves

performance_summary:
  dataset: "5000 legal sentences (test set)"
  metrics:
    OPUS-MT:
      BLEU: 31.94
      ROUGE-L: 0.4412
      ChrF: 53.38
    NLLB-200 (1000-step run):
      BLEU: 41.21
      ROUGE-L: 0.4929
      ChrF: 63.27
  conclusion: "NLLB-200 significantly outperforms OPUS-MT across all metrics."

error_analysis:
  common_errors:
    - Legal terminology mistranslations
    - Clause misalignment
    - Negation errors ("shall not", "may not")
    - Complex multi-clause structures
    - Statute references and abbreviations
    - Style consistency in formal Hindi
  reference_report: report/EE782_Final_Project_Report.pdf
