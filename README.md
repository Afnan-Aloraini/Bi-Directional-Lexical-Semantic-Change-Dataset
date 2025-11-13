# 🧠 BD-LSC: Bi-Directional Lexical Semantic Change  
### A Benchmark Dataset for Tracking Sense Gain, Loss, and Stability in Slang and Standard English

![BD-LSC Banner](docs/assets/banner.png)

---

## 🔍 Overview

**BD-LSC (Bi-Directional Lexical Semantic Change)** is the **first benchmark dataset** designed to detect and analyze *bi-directional* changes in word meaning — capturing how lexical senses are **gained**, **lost**, or **remain stable** across **slang and standard English** from the 1980s to the 2020s.

Unlike traditional binary semantic change datasets (e.g., SemEval-2020 or TempoWiC), BD-LSC introduces **multi-label temporal annotations** across **three time periods** and integrates both **formal corpora (COHA/CCOHA)** and **informal data (Twitter)**, enabling a unified view of language evolution across registers.

---

## 🧱 Dataset Composition

| Period | Years | Source | Description |
|:------:|:------|:--------|:-------------|
| **T1** | 1980–1999 | CCOHA / COHA | Late 20th-century formal written English |
| **T2** | 2000–2009 | COHA | Early 21st-century transitional English |
| **T3** | 2010–2020 | Twitter | Contemporary slang and social media language |

### 📚 Data Sources
- **Standard English:** *COHA*, *CCOHA*, *Oxford English Dictionary (OED)*  
- **Slang:** *SlangSD*, *Green’s Dictionary of Slang*, *Urban Dictionary*, *Online Slang Dictionary*  
- **Annotation Quality:** 3 expert annotators  
  - Cohen’s κ = **0.92 (T1)** / **0.89 (T2)** / **0.86 (T3)**  

Each target word is labeled for *Sense Gain (SG)*, *Sense Loss (SL)*, and *No Change (NC)* between periods **T1→T2**, **T2→T3**, and **T1→T3**.

---

## 💬 Target Words and Example Entries

The BD-LSC dataset includes over **2,000 target words** (8,000+ annotated senses), covering both slang and standard English.

| Word | Example Standard Meaning | Example Slang Meaning | Period | Change Type |
|:------|:--------------------------|:-----------------------|:--------|:--------------|
| **fire** | Combustion | Amazing, cool | T2→T3 | 🟢 Sense Gain |
| **ghost** | Spirit | Ignore or cut off communication | T2→T3 | 🟢 Sense Gain |
| **tea** | Beverage | Gossip, truth (“spill the tea”) | T2→T3 | 🟢 Sense Gain |
| **salty** | Contains salt | Bitter, annoyed | T2→T3 | 🟢 Sense Gain |
| **gay** | Cheerful | Homosexual identity | T1→T2 | 🔴 Sense Loss / 🟢 Gain |
| **mammy** | Mother/nanny stereotype | Slang for abundance | T2→T3 | 🟢 Sense Gain |
| **broke** | Lacking money | Emotionally broken | T1→T3 | 🔴 Sense Shift |

> 🗂️ *Full dataset available in `/data/bd-lsc_full.csv`.*

---

## 📘 Annotation Schema

| Word | Sense ID | Sense Description | T1 | T2 | T3 |
|------|-----------|------------------|----|----|----|
| fire | 1 | Combustion / flames | ✅ | ✅ | ✅ |
| fire | 2 | Slang: “cool”, “excellent” | ❌ | ✅ | ✅ |
| fire | 3 | To dismiss from a job | ✅ | ✅ | ✅ |

**Interpretation:**  
✅ = sense present in that period  
❌ = sense absent  

**Label rules:**
- Sense appears → **Sense Gain (SG)**  
- Sense disappears → **Sense Loss (SL)**  
- Sense persists → **No Change (NC)**  

---

## 🧩 Dataset Creation Pipeline

1. **Word selection:** Overlap of *SlangSD* (48k entries) and *COHA* (169k lemmas).  
2. **Filtering criteria:**  
   - Appears ≥50 times in at least one period  
   - ≥50% frequency variance  
   - Appears in multiple periods  
   - Verified slang sense (via OED, Green’s, Urban, Online Slang Dictionary)  
3. **Annotation:** Manual tagging of standard and slang senses per time slice (T1–T3).  
4. **Validation:** Three annotators, inter-annotator agreement (κ ≈ 0.85–0.92).

---

## 🧬 Research Tasks

### **1️⃣ Lexical Semantic Change Detection (SCD)**
Determine whether a word’s sense is **added**, **lost**, or **stable** between periods.

**Input:** Sense inventories from T1–T3  
**Output:** `{Sense Gain, Sense Loss, No Change}`  

### **2️⃣ Word Sense Disambiguation (WSD)**
Assign each instance of a word its correct sense label across time — essential for capturing evolving slang meanings.

---

## 📊 Baseline Evaluation

| Model | Type | Multi-label Accuracy | Exact Sense Match | Notes |
|--------|------|----------------------|-------------------|--------|
| N-gram ML | Supervised | 0.70 | 0.66 | Good baseline |
| DistilBERT | Supervised | 0.47 | 0.53 | Weak on slang |
| FastText | Supervised | 0.47 | 0.53 | Limited context |
| ALBERT + HDBSCAN | Unsupervised | 0.70 | 0.73 | Robust clustering |
| **GPT-4o (few-shot)** | LLM | **0.818** | **0.908** | 🏆 Best overall |

> **Key insight:** GPT-4o demonstrates exceptional few-shot generalization for slang-driven semantic change.

---

## 📂 Repository Structure

```bash
BD-LSC/
├── data/
│   ├── bd-lsc_full.csv                # Full annotated dataset
│   ├── st-wsd_subset.csv              # 10-word fine-grained subset
│   ├── sources/                       # COHA & Twitter collection scripts
│   └── metadata.json                  # Dataset metadata and stats
│
├── docs/
│   ├── paper_summary.pdf              # Paper summary (Language Resources & Evaluation, 2024)
│   ├── assets/
│   │   └── banner.png
│   └── annotation_guidelines.md
│
├── baselines/
│   ├── supervised_ml/                 # RandomForest, SVM, AdaBoost, etc.
│   ├── unsupervised_umap_hdbscan/     # ALBERT + UMAP + HDBSCAN pipeline
│   └── llm_prompts/                   # GPT-4o & GPT-4o-mini prompt templates
│
├── scripts/
│   ├── preprocess.py
│   ├── annotate.py
│   └── evaluate.py
│
├── LICENSE
├── CITATION.cff
└── README.md
