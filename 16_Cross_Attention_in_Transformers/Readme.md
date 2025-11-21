# Cross Attention in Transformers

Cross attention is a core component of the Transformer **decoder**. It allows the decoder to focus on relevant information from the encoder output while generating each token. This mechanism helps the model align input and output sequences, making it essential for tasks like translation and summarization.

---

## 🔍 What is Cross Attention

In cross attention, the decoder uses:
- Queries from the decoder hidden states  
- Keys and Values from the encoder output  

This means the decoder attends to the encoder representation instead of attending to itself.  
The model learns which parts of the input sequence are important for predicting each next output token.

---

## ⚙️ How Cross Attention Works

1. Encoder produces contextual representations for all input tokens  
2. Decoder takes its current hidden state and forms Query vectors  
3. Encoder outputs are used to form Key and Value vectors  
4. Scaled dot product attention is computed  
   \[
   \text{Attention}(Q, K, V) = \text{softmax}\left(\frac{QK^T}{\sqrt{d_k}}\right) V
   \]
5. The result is a weighted combination of encoder features relevant to the current decoding step  

---

## 🧩 Why Cross Attention is Important

- Allows the decoder to focus on the most relevant parts of the input  
- Helps align input and output tokens  
- Essential for encoder decoder models like T5 and BART  
- Improves translation, question answering, summarization, and many seq2seq tasks  

---

## 📊 Key Characteristics

- Decoder queries, encoder keys and values  
- No masking needed because encoder outputs represent full input context  
- Works between layers of encoder and decoder blocks  
- Supports parallel processing inside each decoding step  

---

## 🔗 Reference Paper

Vaswani, A. et al. (2017). *“Attention Is All You Need”*  
https://arxiv.org/abs/1706.03762
