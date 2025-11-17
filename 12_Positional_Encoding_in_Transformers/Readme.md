# Positional Encoding in Transformers

Transformers process all tokens in parallel, so they don’t have a built-in sense of word order.  
To fix this, **positional encoding** is added to the input embeddings so the model can understand the structure and order of a sequence.

---

## 🔍 Why Positional Encoding is Needed  
Because Transformers don’t use recurrence or convolution, they lack any positional information by default.  
Positional encoding gives the model a notion of position, allowing it to distinguish between sentences like:  
> “the cat chased the dog” vs “the dog chased the cat”

---

## ⚙️ How It Works  
Positional encodings use **sine** and **cosine** functions at different frequencies:  
- For even dimensions (2i):  
  \[
  \text{PE}[pos, 2i] = \sin\left(\frac{pos}{10000^{2i/d_\text{model}}}\right)
  \]  
- For odd dimensions (2i + 1):  
  \[
  \text{PE}[pos, 2i + 1] = \cos\left(\frac{pos}{10000^{2i/d_\text{model}}}\right)
  \]

These functions generate smooth, periodic patterns across positions that help the model learn relative distances too.

---

## ✅ Key Benefits  
- Adds a sense of order without recurrence  
- Works for variable or very long sequences  
- Allows the model to infer **relative distances** between tokens  
- Doesn’t require extra learned parameters (in the fixed version)  

---

## 📚 For More Mathematical Detail  
For a deeper mathematical insight into how positional encoding works and its linear relationships, check this blog post:  
[Linear Relationships in the Transformer’s Positional Encoding](https://blog.timodenk.com/linear-relationships-in-the-transformers-positional-encoding/)

---

## 🔗 Reference Paper  
Vaswani, A. et al. (2017). *“Attention Is All You Need.”*  
[arXiv:1706.03762](https://arxiv.org/abs/1706.03762)  
