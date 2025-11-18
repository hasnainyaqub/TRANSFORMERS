# Layer Normalization in Transformers and Layer Norm vs Batch Norm

Layer normalization is a key component in transformer architectures. It stabilizes training by normalizing activations across the hidden dimensions of each token. This helps the model train faster and remain stable even with very deep layers.

---

## What is Layer Normalization
Layer norm normalizes each individual sample by computing the mean and variance across its features. In transformers, this is usually applied after sublayer operations such as self attention or feed forward networks. It ensures steady gradients and consistent scale throughout the network.

Mathematically,
y = (x minus mean(x)) divided by sqrt(var(x) plus epsilon)

---

## Why Transformers Use Layer Norm Instead of Batch Norm
Transformers process variable length sequences and work with attention mechanisms that treat each position independently. Batch norm depends on batch statistics which change across batches and require consistent batch sizes. This makes batch norm less suitable for sequence to sequence setups where padding, masks, and variable input sizes are common.

Key reasons:
1. Layer norm works on each sample independently and does not depend on batch size  
2. It is stable for sequence models, especially with variable length inputs  
3. It avoids issues with batch statistics changing in attention layers  
4. It enables training with very small batch sizes  
5. It is more compatible with residual connections used in transformers  

---

## Layer Norm vs Batch Norm

### Layer Normalization
- Normalizes across features of a single token  
- Works well for sequence models and transformers  
- Independent of batch size  
- Stable for RNNs, LSTMs, and attention based models  

### Batch Normalization
- Normalizes using statistics from the entire batch  
- Works best for CNNs and vision tasks  
- Depends on large and consistent batch sizes  
- Not ideal for variable length sequences  

---

## Advantages of Layer Normalization in Transformers
- Improves training stability  
- Helps gradients flow better across deep layers  
- Works with residual connections  
- Robust for small batch sizes  
- Reduces internal covariate shift  

---

## Reference Papers
Layer Normalization Paper  
https://arxiv.org/abs/1607.06450

Batch Normalization Paper  
https://arxiv.org/abs/1502.03167
