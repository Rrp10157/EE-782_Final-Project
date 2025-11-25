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

## 📂 Repository Structure

📁 root/
│
├── notebooks/
│ ├── EE782_FinalProject_Opus.ipynb
│ ├── EE782_FinalProject_NLLB_final_submission.ipynb
│
├── data/
│ ├── train_data.xlsx
│ ├── validation_data.xlsx
│ ├── test_data.xlsx
│
├── results/
│ ├── opus_test_en_hi_model_hindi.csv
│ ├── nllb_test_en_hi_model_hindi.csv
│ ├── plots/
│ ├── opus_loss_curve.png
│ ├── opus_bleu_curve.png
│ ├── opus_rougel_curve.png
│ ├── opus_chrf_curve.png
│ ├── nllb_loss_curve.png
│ ├── nllb_bleu_curve.png
│ ├── nllb_rougel_curve.png
│ ├── nllb_chrf_curve.png
│
├── report/
│ ├── EE782_Final_Project_Report.pdf
│
└── README.md
