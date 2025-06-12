# 📰 Fake News Detection in Dravidian Language using Deep Learning

This project applies and compares multiple **Recurrent Neural Network (RNN)** architectures for detecting fake news in **Malayalam**, a Dravidian language. It focuses on binary classification: distinguishing between **Fake** and **Original** news articles.

Four deep learning models are developed and evaluated:

- Simple RNN
- LSTM (Long Short-Term Memory)
- GRU (Gated Recurrent Unit)
- Bi-LSTM (Bidirectional LSTM)

---

## 📑 Table of Contents

- [Project Overview](#project-overview)
- [Methodology](#methodology)
  - [1. Data Preprocessing](#1-data-preprocessing)
  - [2. Model Architectures](#2-model-architectures)
  - [3. Training and Evaluation](#3-training-and-evaluation)
- [📊 Results](#results)
- [🚀 How to Use](#how-to-use)
- [🧩 Dependencies](#dependencies)

---

## 📘 Project Overview

This project demonstrates a practical NLP pipeline for detecting fake news using **deep learning**. By applying four types of RNNs on the same dataset, we aim to assess their relative effectiveness for a language with low-resource NLP tools (Malayalam).

---

## 🧪 Methodology

### 1. Data Preprocessing

The following steps prepare the data for neural network training:

- **Label Encoding:** Converts "Fake" and "Original" into binary values (0, 1) using `LabelEncoder`.
- **Tokenization:** Uses `Tokenizer` from `keras.preprocessing.text` to convert text to integer sequences (top 10,000 words).
- **Padding:** Applies `pad_sequences` to ensure all input sequences are of length 50.
- **Train/Validation Split:** 80% training, 20% validation.

---

### 2. Model Architectures

Each model shares this basic structure:

- **Embedding Layer:** Converts integer sequences to dense word vectors.
- **Recurrent Layer:** One of the following:
  - `SimpleRNN`
  - `LSTM`
  - `GRU`
  - `Bidirectional(LSTM)`
- **Dense Output Layer:** With `sigmoid` activation for binary classification.

All models are compiled with:

- Optimizer: `Adam`
- Loss: `binary_crossentropy`

---

### 3. Training and Evaluation

- Models are trained for **5 epochs** with **batch size 32**
- Accuracy on both training and validation sets is recorded
- A final plot compares the validation accuracy across models

---

## 📊 Results

| Model      | Final Validation Accuracy (Approx.) |
|------------|-------------------------------------|
| Simple RNN | ~70.0%                              |
| LSTM       | ~68.1%                              |
| GRU        | ~68.3%                              |
| Bi-LSTM    | ~78–80%                             |

✅ **Conclusion:**  
The **Bidirectional LSTM** model achieved the best results, likely due to its ability to understand sequence context from both directions, enhancing its grasp of syntactic and semantic patterns in Malayalam.

---

## 🚀 How to Use

1. Clone the repository:

   ```bash
   git clone https://github.com/your-username/fake-news-dravidian.git
   cd fake-news-dravidian
