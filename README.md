
## Case Study: Roman Urdu Classification via XLM-R + HAF-BiGRU

### 📝 Project Abstract

This repository presents a novel deep learning framework designed to navigate the linguistic complexities of South Asian digital communication. By integrating a **Hierarchical Attention Fusion (HAF)** mechanism with a **Bidirectional Gated Recurrent Unit (BiGRU)** head onto an **XLM-RoBERTa** backbone, we achieve robust sentiment detection in **Roman Urdu**—a low-resource, code-mixed script.

> **Research Status:** ✍️ I am currently authoring a research paper detailing this architecture. This repository serves as the official implementation of our experimental results on the **RUWV-NSR** dataset.

---

### 🌍 The Sociolinguistic Context: India’s Regional Diversity

In a country like India, language is not a monolith; it is a rich tapestry of regional dialects and scripts.

* **Regional Complexity:** Every region in India possesses its own unique language and cultural nuances. This diversity makes universal NLP extremely difficult, as standard models often overlook regional linguistic shifts.
* **The Rise of Roman Urdu:** In digital spaces (social media, SMS, chat), users frequently bypass traditional scripts in favor of **Roman Urdu**—writing Urdu using the Latin alphabet.
* **Low-Resource & Code-Mixed:** This medium is "low-resource" (lacking standardized datasets) and heavily "code-mixed" (fusing Urdu with English). Our work focuses on this specific intersection to bridge the gap between regional expression and machine understanding.

---

### ⚠️ The Problem: Linguistic Barriers in Roman Urdu

Analyzing sentiment in Roman Urdu is significantly more complex than standard English or Arabic-script Urdu due to several factors:

1. **Lack of Orthographic Standardization:** It is a phonetic script where users write based on sound. A single word like *"Beautiful"* can be written as *khubsurat*, *khoobsoorat*, or *khubsurt*.
2. **Code-Mixing (Hinglish/Urdu-English):** Sentences frequently mix Urdu and English (e.g., *"Model ki performance amazing hai"*). The AI must be "multilingual" within a single sentence.
3. **Informal "Social Media" Grammar:** Digital chat is full of slang, short-forms, and cultural sarcasm that traditional grammar-based NLP tools fail to detect.
4. **Data Scarcity:** While English has billions of training tokens, Roman Urdu is a **low-resource** language with very few high-quality, balanced datasets.

---

### 🧬 Why These Techniques? (The Research Rationale)

#### **1. XLM-RoBERTa (The Backbone)**

* **Problem:** Roman Urdu is fundamentally **Code-Mixed**.
* **The "Why":** XLM-R is pre-trained on 100+ languages. It provides a "shared space" where the model understands the context of both Urdu and English words simultaneously.

#### **2. Bi-GRU Layer (Gated Recurrent Units)**

* **Problem:** Informal text lacks strict grammar and contains long, rambling structures.
* **The "Why":** GRUs capture long-range dependencies efficiently. By using a **Bidirectional** GRU, the model reads the sentence from both ends, helping it understand the "flow" and context of informal regional phrases.

#### **3. Hierarchical Attention Fusion (HAF)**

* **Problem:** Certain regional keywords carry the entire emotional weight of a sentence.
* **The "Why":** HAF fuses information from multiple internal layers of the Transformer. This allows the model to focus its "attention" on the most sentiment-heavy regional keywords.

---

### 📸 Seen on Screen

#### **1. Neural Architecture**

The transition from a transformer encoder to a custom sequential-attention head.


#### **2. Overcoming Data Scarcity (EDA Results)**

We utilized **Easy Data Augmentation (EDA)** to balance the dataset, specifically expanding the "Neutral" class to prevent model bias.
| Class | Original Samples | After EDA Augmentation |
| :--- | :--- | :--- |
| **Negative** | 8,279 | 8,279 |
| **Neutral** | 5,156 | **15,436** (+300% Growth) |
| **Positive** | 9,037 | 9,037 |

---

### 🔬 Methodology (Research Breakdown)

| Component | Implementation | Research Purpose |
| --- | --- | --- |
| **Encoder** | `xlm-roberta-base` | Code-Mixing & Multilingual Context |
| **Gated Layer** | **Bi-GRU** | Long-range Sequential Dependencies |
| **Attention** | **HAF** | Hierarchical Keyword Weighting |
| **Data Strategy** | **EDA** | Low-Resource Class Balancing |
| **Accuracy** | **73.09%** | High-Precision Regional Optimization |


---

### 📚 References & Research

* **Paper In-Progress:** Shakir, M. (2026). *Hybrid Attention-Recurrent Networks for Regional Code-Mixed Sentiment Analysis.*
* **Dataset:** Ahmed, M. (2024). *RUWV-NSR (v5)*. Mendeley Data.


---

**Maintained by Mohd Shakir** *PhD Scholar | Language Education & AI | New Delhi, India*
