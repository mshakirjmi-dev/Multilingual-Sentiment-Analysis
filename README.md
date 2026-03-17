
---

# Roman Urdu Sentiment Analysis via XLM-R + HAF-BiGRU

### 📝 Project Overview

In a linguistically diverse country like **India**, standard NLP models often fail to capture regional nuances. This project focuses on **Roman Urdu**—a low-resource, code-mixed script used widely in digital communication. We move beyond basic transformers to a hybrid **HAF-BiGRU** architecture to handle the specific "noise" of informal regional text and the complexities of local dialects.

> **Status:** ✍️ Research paper currently in progress. This repository contains the official implementation of the **HAF-BiGRU** framework.

---

### 🌍 The Sociolinguistic Context

India is a land of regional languages where every region has its own unique linguistic identity.

* **The Regional Challenge:** Universal models struggle with India's regional diversity. Standard scripts are often replaced in digital chat by **Roman Urdu** (Urdu words in Latin characters).
* **Code-Mixed & Low-Resource:** This script is heavily "code-mixed" (Urdu + English) and lacks the massive datasets available for English, making it a "low-resource" challenge that requires specialized AI architectures.

---

### 🧬 Why These Techniques? (The Research Rationale)

Each layer of our architecture is specifically chosen to address the hurdles of regional, informal text:

#### **1. XLM-RoBERTa (The Backbone)**

* **The Problem:** Roman Urdu is fundamentally **Code-Mixed**. English-only models cannot understand Urdu context, and monolingual models fail on English loanwords.
* **The "Why":** **XLM-R** is a multilingual powerhouse. It provides a shared understanding across both languages, allowing the model to process a sentence that switches between Urdu and English seamlessly.

#### **2. Bi-GRU Layer (Gated Recurrent Units)**

* **The Problem:** Informal regional text lacks strict grammar and often contains long, rambling sentence structures.
* **The "Why":** **GRUs** are highly efficient at capturing long-range dependencies. By using a **Bidirectional** GRU, the model reads the sentence from both ends, helping it understand the "flow" and context of informal Urdu phrases more effectively than a standard linear layer.

#### **3. Hierarchical Attention Fusion (HAF)**

* **The Problem:** In regional communication, certain keywords carry the entire emotional weight of a sentence (e.g., *"Weather bura hai par mood acha hai"*).
* **The "Why":** **HAF** doesn't just look at the final output; it "fuses" information from multiple internal layers of the Transformer. This allows the model to focus its "attention" on the most sentiment-heavy regional keywords, improving accuracy in noisy text.

---

### 📸 Seen on Screen

#### **1. Neural Architecture Diagram**

#### **2. Solving Data Scarcity (EDA Results)**

Because Roman Urdu is low-resource, we used **Easy Data Augmentation (EDA)** to balance the dataset.
| Class | Before EDA | After EDA |
| :--- | :--- | :--- |
| **Neutral** | 5,156 | **15,436** (3x Increase) |

---

### 🧪 Methodology Summary

| Component | Implementation | Target Problem |
| --- | --- | --- |
| **Encoder** | XLM-RoBERTa | Code-Mixing & Multilingualism |
| **Gated Layer** | **Bi-GRU** | Long-range Sentence Dependencies |
| **Attention** | **HAF** | Hierarchical Keyword Weighting |
| **Strategy** | **EDA** | Low-Resource Data Scarcity |
| **Result** | **73.09% Accuracy** | Regional Script Optimization |

---


**Maintained by Mohd Shakir** *PhD Scholar | Language Education & AI | New Delhi, India*
