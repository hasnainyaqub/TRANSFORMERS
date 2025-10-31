# Bahdanau Attention vs. Luong Attention

This note compares two prominent attention mechanisms used in sequence-to-sequence models: Bahdanau (additive) and Luong (multiplicative) attention.

## 🔗 Research Papers  
- Bahdanau Attention: “Neural Machine Translation by Jointly Learning to Align and Translate” (https://arxiv.org/abs/1409.0473) :contentReference[oaicite:2]{index=2}  
- Luong Attention: “Effective Approaches to Attention-based Neural Machine Translation” (https://arxiv.org/abs/1508.04025) :contentReference[oaicite:3]{index=3}  

## 🧠 What Each Mechanism Does  
- **Bahdanau Attention (Additive)**: The decoder computes alignment scores based on the decoder’s previous hidden state and each encoder hidden state via a feed-forward network. :contentReference[oaicite:4]{index=4}  
- **Luong Attention (Multiplicative / Dot-Product / General)**: The decoder uses its current hidden state and the encoder hidden states in a simpler scoring function (dot-product, general, or concat) and attends globally or locally. :contentReference[oaicite:5]{index=5}  

## 📊 Key Differences  
| Feature                          | Bahdanau (2014)                               | Luong (2015)                                  |
|----------------------------------|-----------------------------------------------|-----------------------------------------------|
| Score function                   | Additive (feed-forward)                        | Dot-product, General, Concat                   |
| Uses decoder **previous** state | ✔                                            | ✖ (uses current state)                         |
| Attention scope                  | Implicitly global                              | Global and Local variants                      |
| Complexity & speed               | Slightly heavier                              | Simpler & faster in many cases                 |
| Typical use-case                | Robust alignment for long input sequences     | Efficient attention, often used in practise   :contentReference[oaicite:6]{index=6}  

## 🛠 Why It Matters  
Choosing the right attention mechanism affects model performance and complexity.  
- Bahdanau’s method helps with very long sequences by focusing adaptively.  
- Luong’s method introduces efficiency and variant choices (global vs local) which may fit production settings better. :contentReference[oaicite:7]{index=7}  

## 📚 Further Reading  
- For implementation details and code examples, check tutorials on Bahdanau vs Luong attention.  
- For a deeper dive into attention mechanisms, see also the broader “Attention Is All You Need” paper (2017) which extends these ideas to the Transformer architecture. :contentReference[oaicite:8]{index=8}  

## ✅ Summary  
Both mechanisms are foundational in modern NLP.  
Use Bahdanau for flexible alignment in complex settings; use Luong for efficient and varied alignment schemes in production-oriented models.

