# Masked Multi-Head Attention in Transformers

Masked Multi-Head Attention is a key component in the **decoder** of the Transformer architecture.  
It allows the model to generate outputs sequentially while preventing it from "seeing the future" tokens during training.

---

## 🔍 What is Masked Multi-Head Attention

In standard multi-head attention, each token can attend to all tokens in the input sequence.  
In **masked multi-head attention**, tokens in the decoder can only attend to **previous tokens and the current token**, not future tokens.  

This ensures the model learns **autoregressive behavior** for tasks like text generation.

---

## ⚙️ How Masked Attention Works

1. Compute Query (Q), Key (K), and Value (V) vectors for all tokens in the decoder input.  
2. Calculate attention scores using scaled dot-product attention:  
   \[
   \text{Attention}(Q, K, V) = \text{softmax}\left(\frac{QK^T}{\sqrt{d_k}} + M\right) V
   \]  
   where **M** is the mask matrix that sets scores for future tokens to negative infinity.  
3. Apply softmax to get attention weights, which ignore masked positions.  
4. Multiply weights with Value vectors to get the final context-aware representation for each token.  

---

## 🧩 Why Masking is Important

- Prevents information leakage from future tokens  
- Ensures proper autoregressive training for language generation  
- Enables sequential decoding while still using multi-head attention  
- Keeps the model aligned with how it will be used during inference

---

## 📊 Applications

- Language generation models (GPT, Transformer decoders)  
- Autoregressive machine translation  
- Text summarization and completion tasks  

---

## 🔗 Reference Paper

Vaswani, A. et al. (2017). *“Attention Is All You Need”*  
[https://arxiv.org/abs/1706.03762](https://arxiv.org/abs/1706.03762)
