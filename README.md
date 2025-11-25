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

```bash
pip install transformers datasets sentencepiece sacrebleu evaluate accelerate rouge-score


## 🏋️ Training Instructions
OPUS-MT Fine-Tuning

Open the notebook: notebooks/EE782_FinalProject_Opus.ipynb


Run end-to-end in Google Colab (T4 GPU recommended).
The training loop includes:

Tokenization

Preprocessing

Fine-tuning for 1000 steps

Validation BLEU, ROUGE-L, ChrF

Test set inference

Plot generation

NLLB-200 Fine-Tuning

Open:

notebooks/EE782_FinalProject_NLLB_final_submission.ipynb


This notebook:

Loads multilingual tokenizer with eng_Latn / hin_Deva

Enables gradient checkpointing to fit model on Colab GPU

Fine-tunes for up to 1000 steps

Produces output CSV + performance metrics

Logs training curves

📈 Performance Summary
Final Test Set Metrics (5000 legal sentences)
Model	BLEU	ROUGE-L	ChrF
OPUS-MT	31.94	0.4412	53.38
NLLB-200 (1000-step run)	41.21	0.4929	63.27

NLLB-200 significantly outperforms OPUS-MT across all metrics.

🔍 Error Types Observed

Common translation challenges include:

Legal terminology mistranslations

Clause misalignment

Negation errors (“shall not”, “may not”)

Complex multi-clause structures

Statute references and abbreviations

Style consistency in formal Hindi

Detailed analysis in:
report/EE782_Final_Project_Report.pdf

