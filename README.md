This is a systematic, research-oriented GitHub README structure for your project. It presents your work as a formal study, highlighting the methodology and your ongoing paper.

---

# Sentiment Analysis of Roman Urdu using XLM-RoBERTa with HAF-BiGRU

## 📖 Abstract

This project focuses on the sentiment classification of **Roman Urdu**, a low-resource language variant. We propose a hybrid architecture combining the multilingual capabilities of **XLM-RoBERTa** with a custom **Hierarchical Attention Fusion (HAF)** and **Bidirectional Gated Recurrent Unit (BiGRU)** classification head. Our approach addresses the phonetic inconsistencies and informal nature of Roman Urdu, achieving significant performance improvements.

---

## 🛑 Problem Statement: The Challenges of Roman Urdu

The computational analysis of Roman Urdu is hindered by several unique linguistic barriers:

1. **Lexical Variation (Phonetic Inconsistency):** Lack of standardized spelling (e.g., *"khubsurat"* vs. *"khoobsoorat"*).
2. **Code-Switching:** Frequent mixing of English and Urdu within a single sentence.
3. **Ambiguity:** Morphologically similar words carrying different meanings based on context.
4. **Data Scarcity:** Limited availability of high-quality, balanced, and labeled datasets for training deep learning models.

---

## 🧪 Methodology & Architecture

### 1. Model Architecture

Our framework replaces the standard linear classification head of XLM-RoBERTa with a specialized **HAF-BiGRU** stack:

* **Encoder:** Pre-trained `xlm-roberta-base` for deep contextual embeddings.
* **BiGRU Layer:** Captures forward and backward long-range dependencies in the text.
* **Hierarchical Attention (HAF):** A mechanism that assigns weights to different hidden states, allowing the model to focus on sentiment-bearing keywords regardless of their position.

### 2. Data Augmentation (EDA)

To resolve the class imbalance found in the **RUWV-NSR dataset**, we applied **Easy Data Augmentation (EDA)**.

* **Neutral Class Expansion:** We increased the Neutral samples from ~5,000 to over 15,000 using synonym replacement and random insertion to ensure a robust, non-biased training process.

---

## 📊 Experimental Results

The model was evaluated on the RUWV-NSR benchmark. Below is a comparison of the key metrics achieved:

| Metric | Score |
| --- | --- |
| **Accuracy** | **73.09%** |
| **Macro F1-Score** | **70.21%** |
| **Dataset Used** | RUWV-NSR (Ahmed, 2024) |
| **Hardware** | NVIDIA Tesla T4 |

### Visualizations

---

## 📝 Ongoing Research

I am **currently authoring a research paper** detailing this architecture and its comparative performance against standard Transformer models. The paper explores:

* The effectiveness of Attention Fusion in informal Roman Urdu.
* The impact of EDA on multilingual model convergence.
* Hyperparameter optimization for BiGRU-based heads in NLP.

---

## 🚀 Getting Started

### Installation

```bash
git clone https://github.com/your-username/roman-urdu-sentiment.git
cd roman-urdu-sentiment
pip install -r requirements.txt

```

### Inference Snippet

```python
import torch
from model import XLMR_HAF_BiGRU

# Load trained model weights
model = XLMR_HAF_BiGRU.load_from_checkpoint('./final_xlmr_haf_bigru/')
# Predict sentiment
text = "Bohat hi zabardast performance hai model ki!"
prediction = model.predict(text)
print(f"Sentiment: {prediction}")

```
