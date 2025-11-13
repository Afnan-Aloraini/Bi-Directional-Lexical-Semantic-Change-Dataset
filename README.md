# 🧠 BD-LSC: Bi-Directional Lexical Semantic Change  
### A Benchmark Dataset for Tracking Sense Gain, Loss, and Stability in Slang and Standard English

---

## 🔍 Overview

BD-LSC (Bi-Directional Lexical Semantic Change) is the first benchmark dataset designed to detect and analyze bi-directional changes in word meaning, capturing how lexical senses are gained, lost, or remain stable across slang and standard English from the 1980s to the 2020s.

Unlike traditional binary semantic change datasets (e.g., SemEval-2020 or TempoWiC), BD-LSC introduces multi-label temporal annotations across three time periods and integrates both formal corpora (COHA/CCOHA) and informal data (Twitter), enabling a unified view of language evolution across registers.

---

## 🧱 Dataset Composition

| Period | Years | Source | Description |
|:------:|:------|:--------|:-------------|
| T1 | 1980–1999 | CCOHA / COHA | Late 20th-century formal written English |
| T2 | 2000–2009 | COHA | Early 21st-century transitional English |
| T3 | 2010–2020 | Twitter | Contemporary slang and social media language |

### 📚 Target words Sources
- Standard English: COHA, CCOHA, Oxford English Dictionary (OED)  
- Slang: SlangSD, Green’s Dictionary of Slang, Urban Dictionary, Online Slang Dictionary  
- Annotation Quality: 3 expert annotators  
  - Cohen’s κ = 0.92 (T1) / 0.89 (T2) / 0.86 (T3)  

Each target word is labeled for Sense Gain (SG), Sense Loss (SL), and No Change (NC) between periods T1→T2, T2→T3, and T1→T3.

---

## 💬 Target Words and Example Entries

The BD-LSC dataset includes 79 target words (8,000+ annotated senses), covering both slang and standard English.

| Word | Example Standard Meanings | Example Slang Meanings | Period | Change Type |
|:------|:---------------------------|:-------------------------|:--------|:--------------|
| fire | Combustion, flames; to dismiss from a job; enthusiasm or passion | Excellent, cool, exciting; attractive person; to insult someone online (fire shots) | T2→T3 | 🟢 Sense Gain |
| ghost | Spirit or apparition; faint image or trace | To ignore or suddenly cut off communication; to disappear from social media; a hidden online account | T2→T3 | 🟢 Sense Gain |
| tea | Beverage made from leaves; letter "T" as a symbol | Gossip, truth, or personal information ("spill the tea"); energy or stimulant (from “vitamin T”) | T2→T3 | 🟢 Sense Gain |
| salty | Tasting of salt; seasoned or maritime-related | Bitter, annoyed, resentful; harsh or offensive; sexually suggestive | T2→T3 | 🟢 Sense Gain |
| gay | Cheerful, happy, bright; carefree or lively | Homosexual identity; used pejoratively in informal speech (now reclaimed); fashionable or vibrant | T1→T2 | 🔴 Sense Loss / 🟢 Sense Gain |
| mammy | Mother; nanny; affectionate term for maternal figure | Term for abundance (“money’s mammy” = a lot of money); brand or song name; derogatory racial stereotype | T2→T3 | 🟢 Sense Gain |
| broke | Lacking money; destroyed or damaged; fractured | Emotionally exhausted or depressed; completely without resources; person with no financial stability | T1→T3 | 🔴 Sense Shift |
| plug | Electrical connector; stopper for a hole | Supplier or dealer (e.g., for goods or drugs); promoter or endorsement (e.g., “give me a plug”); social contact | T2→T3 | 🟢 Sense Gain |
| drip | Falling liquid; sound of dripping; slow flow | Fashion sense or stylish outfit; jewelry or luxury appearance; confidence or swagger | T2→T3 | 🟢 Sense Gain |
| lit | Past tense of “light”; illuminated | Exciting, fun, energetic; intoxicated; excellent or popular | T2→T3 | 🟢 Sense Gain |
| sick | Ill or unwell; morally wrong | Amazing, impressive, cool; disturbing or twisted (dark humor); physically strong | T2→T3 | 🟢 Sense Gain |
| troll | Mythical creature under a bridge; fishing method | Online harasser or provocateur; to bait someone online; person causing arguments intentionally | T1→T2 | 🟢 Sense Gain |
| cloud | Visible mass of water vapor; weather formation | Online data storage (“in the cloud”); mood or mental state; tech ecosystem | T1→T2 | 🟢 Sense Gain |
| flex | To bend or tighten muscles; to demonstrate power | To show off, boast, or flaunt possessions; to act confidently or arrogantly | T2→T3 | 🟢 Sense Gain |
| bread | Baked food made from flour; staple food | Money, income, wealth (“get that bread”); livelihood or resources | T2→T3 | 🟢 Sense Gain |
| keyboard | Musical instrument; panel of keys | Computer input device; set of digital keys on a phone or app | T1→T2 | 🟢 Sense Gain |
| mouse | Small rodent; timid person | Computer input device; person spying or lurking online | T1→T2 | 🟢 Sense Gain |
| viral | Relating to viruses or infections | Extremely popular or rapidly spreading online; meme or post with wide reach | T2→T3 | 🟢 Sense Gain |
| chronic | Long-lasting or persistent (medical term) | High-quality cannabis; intense or extreme (positive or negative); title of Dr. Dre album | T2→T3 | 🟢 Sense Gain |
| mad | Angry or insane; irrational | Extremely or very (e.g., “mad skills”); expressive or exaggerated slang intensifier | T1→T3 | 🟢 Sense Gain |


🗂️ Full dataset available in `/data/bd-lsc_full.csv`.

---

## 📘 Annotation Schema

| Word | Sense ID | Sense Description | T1 | T2 | T3 |
|------|-----------|------------------|----|----|----|
| fire | 1 | Combustion / flames | ✅ | ✅ | ✅ |
| fire | 2 | Slang: “cool”, “excellent” | ❌ | ✅ | ✅ |
| fire | 3 | To dismiss from a job | ✅ | ✅ | ✅ |

Interpretation:  
✅ = sense present in that period  
❌ = sense absent  

Label rules:
- Sense appears → Sense Gain (SG)  
- Sense disappears → Sense Loss (SL)  
- Sense persists → No Change (NC)  

---

## 🧩 Dataset Creation Pipeline

1. Word selection: Overlap of SlangSD (48k entries) and COHA (169k lemmas).  
2. Filtering criteria:  
   - Appears ≥50 times in at least one period  
   - ≥50% frequency variance  
   - Appears in multiple periods  
   - Verified slang sense (via OED, Green’s, Urban, Online Slang Dictionary)  
3. Annotation: Manual tagging of standard and slang senses per time slice (T1–T3).  
4. Validation: Three annotators, inter-annotator agreement (κ ≈ 0.85–0.92).

---

## 🧬 Research Tasks

### 1️⃣ Lexical Semantic Change Detection (SCD)
Determine whether a word’s sense is added, lost, or stable between periods.

Input: Sense inventories from T1–T3  
Output: {Sense Gain, Sense Loss, No Change}  


## 📊 Baseline Evaluation

| Model | Type | Multi-label Accuracy | Exact Sense Match | Notes |
|--------|------|----------------------|-------------------|--------|
| N-gram ML | Supervised | 0.70 | 0.66 | Good baseline |
| DistilBERT | Supervised | 0.47 | 0.53 | Weak on slang |
| FastText | Supervised | 0.47 | 0.53 | Limited context |
| ALBERT + HDBSCAN | Unsupervised | 0.70 | 0.73 | Robust clustering |
| GPT-4o (few-shot) | LLM | 0.818 | 0.908 | 🏆 Best overall |

Key insight: GPT-4o demonstrates exceptional few-shot generalization for slang-driven semantic change.

---


