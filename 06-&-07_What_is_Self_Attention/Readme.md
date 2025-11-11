# 🧠 What is Self-Attention? | Self-Attention in Transformers

Self-Attention is the core mechanism that powers Transformer architectures.  
It allows each token in a sequence to attend to every other token, enabling the model to understand relationships and dependencies regardless of their position in the input.  

---

## 🔍 What is Self-Attention?

In simple terms, **Self-Attention** computes how much focus each word (or token) should give to other words when building its representation.  
Unlike RNNs or LSTMs that process tokens sequentially, Self-Attention looks at the **entire sequence at once**, capturing both nearby and distant dependencies efficiently.

---

## ⚙️ How It Works

For each token, the model creates three vectors:

- **Query (Q)** – What the current token is asking for  
- **Key (K)** – What each other token offers as context  
- **Value (V)** – The actual information of each token  

Then the model computes an attention score by comparing Queries and Keys:

\[
\text{Attention}(Q, K, V) = \text{softmax}\left(\frac{QK^T}{\sqrt{d_k}}\right)V
\]

- The **dot product (QKᵀ)** measures similarity between tokens.  
- The **softmax** normalizes scores into probabilities.  
- The output is a weighted sum of all Values (V), showing how much each token contributes to the current one.

---

## 🧩 Why Self-Attention Matters

- Captures **long-range dependencies** that RNNs struggle with  
- Processes all tokens **in parallel**, making training faster  
- Learns **contextual meaning** dynamically, adjusting focus per token  
- Enables scalability to massive datasets and large models  

---

## 🌐 Self-Attention in Transformers

The Transformer architecture stacks multiple **Self-Attention layers** within both the **encoder** and **decoder**.  
Each layer refines the contextual representation of tokens.  
There are typically two main types:

1. **Encoder Self-Attention:** Each word attends to all others in the input sequence.  
2. **Decoder Self-Attention:** Each word attends to previous words only (using masking) to prevent “seeing the future” during training.  

This mechanism lets models like **BERT**, **GPT**, and **T5** understand complex relationships in text, images, and even multimodal data.

---

## ⚡ Multi-Head Attention

Instead of computing one attention map, Transformers use **multiple attention heads** that run in parallel.  
Each head focuses on different types of relationships — syntax, semantics, position, etc.  
Their outputs are then concatenated and passed through a feed-forward network for richer contextual understanding.

---

## 📚 Example

For the sentence:  
> “The cat sat on the mat.”

When processing the word **“cat”**, self-attention lets the model look at **“the”**, **“sat”**, and **“mat”** to understand full context, rather than only the previous word.

---

## 💡 Advantages

- Handles long-distance relationships effectively  
- Enables full sequence parallelization  
- Learns richer representations for downstream tasks  
- Improves translation, summarization, and reasoning capabilities  

---

## ⚠️ Limitations

- Computationally expensive for very long sequences (O(n²) complexity)  
- Requires large memory for long inputs  
- May overfit without enough data or proper regularization  

---

## 🔬 In Short

Self-Attention helps a model **focus on what matters** in the input sequence.  
It’s the foundation that makes Transformers powerful, flexible, and scalable across modern AI applications.

---

## 📚 References

- Vaswani, A. et al. (2017). [Attention Is All You Need](https://arxiv.org/abs/1706.03762)  
- Jay Alammar, *“The Illustrated Transformer”* – [Blog](https://jalammar.github.io/illustrated-transformer/)  
- Islam, S. et al. (2023). [A Comprehensive Survey on Applications of Transformers for Deep Learning Tasks](https://arxiv.org/pdf/2306.07303)
