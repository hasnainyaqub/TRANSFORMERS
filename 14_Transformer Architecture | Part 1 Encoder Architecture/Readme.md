# Transformer Architecture | Part 1: Encoder Architecture

The Transformer model introduced by Vaswani et al. (2017) uses an **encoder-decoder architecture** with self-attention and feed-forward layers. This section focuses on the **encoder**, which converts input sequences into rich contextual representations.

---

## 🔍 Encoder Overview

The encoder is made of **stacked identical layers**, typically 6 in the original paper. Each layer has two main sublayers:

1. **Multi-Head Self-Attention:**  
   - Allows each token to attend to all other tokens in the sequence  
   - Captures relationships and context at different positions  
   - Parallelizable for faster computation

2. **Feed-Forward Network (FFN):**  
   - Position-wise fully connected layers  
   - Applies non-linear transformation to each token  
   - Improves representation power

Each sublayer is followed by:
- **Residual Connection:** Adds input to output of sublayer  
- **Layer Normalization:** Stabilizes and normalizes activations  

---

## ⚙️ Encoder Input

- **Input Embeddings:** Converts tokens into vectors  
- **Positional Encoding:** Adds order information to embeddings so model can distinguish positions  
- Sum of input embeddings and positional encoding is fed to the first encoder layer

---

## 🧩 Step-by-Step Flow

1. Input tokens → Embeddings + Positional Encoding  
2. Pass through **Multi-Head Self-Attention** with residual and layer norm  
3. Pass through **Feed-Forward Network** with residual and layer norm  
4. Output is passed to next encoder layer  
5. Final encoder output is fed to decoder and/or downstream tasks

---

## 📊 Key Features

- Parallel processing of tokens  
- Captures long-range dependencies  
- Modular and scalable (stack multiple layers)  
- Compatible with various NLP tasks such as translation, summarization, and classification

---

## 🔗 Reference Paper

Vaswani, A. et al. (2017). *“Attention Is All You Need”*  
[https://arxiv.org/abs/1706.03762](https://arxiv.org/abs/1706.03762)
