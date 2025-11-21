# Transformer Decoder Architecture

The decoder is one of the two main components of the Transformer model introduced in the paper “Attention Is All You Need.” It generates output sequences one token at a time while attending to both previously generated tokens and the encoder output. The decoder uses attention mechanisms, residual connections, and feed forward networks to produce coherent and context aware outputs.

---

## 🔍 Decoder Overview

The decoder is made of stacked layers, usually the same number as the encoder. Each layer has three sublayers:

1. **Masked Multi Head Self Attention**  
   - Allows the decoder to attend to previous tokens  
   - Uses a mask to block future tokens  
   - Ensures autoregressive generation

2. **Cross Attention (Encoder Decoder Attention)**  
   - Uses queries from the decoder  
   - Uses keys and values from the encoder output  
   - Helps align input and output sequences

3. **Feed Forward Network**  
   - Applies two linear layers with a non linear activation  
   - Helps the model learn richer representations

Each sublayer uses a residual connection followed by layer normalization.

---

## ⚙️ Decoder Input

- The decoder receives the previously generated tokens  
- Tokens are converted to embeddings  
- Positional encoding is added to provide order information  
- Masking ensures the model does not look ahead

---

## 🧩 Step by Step Flow

1. Decoder input tokens → embeddings plus positional encoding  
2. Pass through masked self attention with residual and layer norm  
3. Pass through cross attention using encoder output  
4. Pass through feed forward network with residual and layer norm  
5. Output flows through next decoder layer  
6. Final decoder output is passed to a linear layer and softmax to predict next token

---

## 📊 Key Features of the Decoder

- Autoregressive generation  
- Masking in self attention to prevent future token leakage  
- Cross attention to capture encoder information  
- Stacked layers for depth and expressiveness  
- Parallel operations inside each layer

---

## 🔗 Reference Paper

Vaswani, A. et al. (2017). “Attention Is All You Need”  
https://arxiv.org/abs/1706.03762
