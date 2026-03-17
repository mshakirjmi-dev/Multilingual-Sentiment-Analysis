---

# Sentiment Analysis of Roman Urdu via XLM-R + HAF-BiLSTM-GRU

### Advancing Multilingual Transformers for Regional Code-Mixed Text

## 📖 Abstract

Digital communication in India and South Asia is characterized by a rich tapestry of regional diversity, where users frequently employ **Roman Urdu** (Urdu in Latin script) mixed with English (code-switching). This project proposes a novel hybrid architecture that integrates **Hierarchical Attention Fusion (HAF)** with **Bi-LSTM** and **Bi-GRU** layers on an **XLM-RoBERTa** backbone. This framework specifically targets phonetic inconsistencies and emotional intensifiers in non-standard scripts, achieving a **73.09% accuracy** on the RUWV-NSR benchmark.

> **Research Status:** ✍️ I am currently authoring a formal research paper detailing these experimental results and the impact of sequential memory on informal regional text classification.

---

## 🛑 The Problem: Linguistic Barriers in Regional NLP

India’s regional languages present several hurdles that standard English-centric models cannot overcome:

1. **Orthographic Inconsistency:** Lack of standard spelling (e.g., *"acha"*, *"achha"*, *"axha"*) creates massive lexical noise.
2. **Character Elongation:** Users repeat characters for emphasis (e.g., *"soooo"* or *"bohaaaaat"*). Standard tokenizers treat these as unique, unknown words.
3. **Low-Resource Data:** Regional code-mixed datasets are often small and highly imbalanced.

---

## 🧪 Methodology & Innovation

### 1. Hybrid HAF-BiLSTM-GRU Architecture

Instead of using a standard linear head, this model utilizes a complex sequential-attention stack:

* **Encoder:** `xlm-roberta-base` provides multilingual embeddings for 100+ languages, ideal for code-mixed Urdu-English text.
* **Memory Layer (Bi-LSTM):** Specifically addresses the **elongation problem**. By maintaining a long-term cell state, the model learns that repeating "o"s represent an emotional intensifier rather than a new word.
* **Gated Layer (Bi-GRU):** Captures long-range dependencies in informal sentence structures.
* **Attention Fusion (HAF):** Extracts `[CLS]` tokens from the last **4 encoder layers** and applies learned softmax attention, focusing the model on the most sentiment-relevant regional keywords.

### 2. Strategic Data Balancing (EDA)

The original RUWV-NSR dataset was significantly imbalanced (~5k Neutral vs ~9k Positive/Negative). We applied **Easy Data Augmentation (EDA)**:

* **Neutral Expansion:** Increased Neutral samples from **5,156 to 15,436** using synonym replacement and random insertion.
* **Result:** Prevented model bias toward extreme sentiments and improved the **Macro F1-score**.

---

## 📊 Experimental Results

| Metric | Baseline (Standard Head) | Our HAF-BiLSTM-GRU |
| --- | --- | --- |
| **Accuracy** | ~68% | **73.09%** |
| **Macro F1-Score** | ~65% | **70.21%** |
| **Precision (Macro)** | ~67% | **71.56%** |

### 📸 Seen on Screen

*Figure 1: Neural Architecture & Dataset Expansion Statistics*

---

