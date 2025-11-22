# Transformer Inference | How Inference is Done in a Transformer

Inference in a transformer refers to the process of generating output tokens after training is complete. Unlike training where full sequences are available, inference is autoregressive which means the model generates one token at a time. Each new token becomes input for the next step until a complete sequence is produced.

---

## 🔍 How Transformer Inference Works

During inference, the decoder does not have access to the entire target sentence. It starts with a start token and predicts the next token step by step.

### Step by Step Process

1. **Start Token**
   The decoder receives a start token as the first input.

2. **Masked Self Attention**
   The decoder attends only to previously generated tokens. Future positions remain masked.

3. **Cross Attention**
   The decoder attends to the encoder output to understand the input context.

4. **Predict Next Token**
   The output passes through a linear layer and softmax to predict the next token.

5. **Append and Repeat**
   The predicted token is added to the sequence and becomes input for the next step.

6. **Stop Condition**
   Generation stops when an end token appears or the maximum length is reached.

---

## 🧠 Decoding Strategies

Transformers support different decoding strategies.

### Greedy Decoding
Selects the highest probability token at each step. Fast but may miss better sequences.

### Beam Search
Tracks multiple candidate sequences at once. Produces higher quality outputs.

### Sampling
Randomly samples tokens based on probability distribution. Good for creative generation.

### Top k and Top p Sampling
Limits sampling to a subset of high probability tokens to balance randomness and quality.

---

## 📊 Key Characteristics of Inference

- Autoregressive generation  
- One token generated at a time  
- Masked self attention ensures no future token access  
- Encoder output reused in every decoding step  
- Choice of decoding strategy affects quality and speed  

---

## 🔗 Reference Paper

Vaswani, A. et al. (2017). “Attention Is All You Need”  
https://arxiv.org/abs/1706.03762
