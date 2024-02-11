![image](https://github.com/bala1802/LLM_From_Scratch/assets/22103095/76bc6f7d-eff3-4a1c-94cb-1c15e1015b5c)


# LLM_From_Scratch
Explore the journey of training a powerful language model from the ground up. This repository documents the process, challenges, and insights gained while developing a Large Language Model from scratch.

## Rotary Positional Embeddings (RoPE)

What is a Rotary Positional Embeddings and how do they combine the best of Absolute Positional Embeddings & Relative Positional Embeddings.

Why do we need Positional Embeddings in the first place?

The reason is that, the Transformers models are invariant to order by default. So the Sentence like

- The Man escaped from the Snake
- The Snake escaped from the Man

The above sentences have same representation, eventhough the semantic meaning is different. Or even anyother combination of words may also result in a different meaning.

Because all of these tokens are basically fed into the Transformer as an unordered Set. If you want to preserve the order information, then you need to add in the Positional information somehow

### Absolute Positional Embeddings

Let's say you have an Embedding that represents one word in a sentence, then to represent the positional information we have a vector of the same dimension as the word itself. So each one of these vectors represents one specific position in a sentence. For example, position 2 meaning a second word in a sentence, and each possible sentence Position will be represented by a different vector. 


![alt text](Visuals/01_AbsolutePositionalEmbedding.png)

Then we simply add together the word embedding and the positional Embedding to produce the Input for the Transformer Layer. There are two main ways you can generate these Positional Embeddings

![alt text](Visuals/02_AbsoultePositionalEmbedding.png)

1) The First Method is to simply learn them from data, just like the rest of the parameters of the Model. So we would learn one positional vector for position one, for position two and so on up to the maximum length that you want to represent. This is problem becuase the maximum length that you can represent is bounded. If you only learn positional vectors upto position say 512, then there is no way to represent a sequence of longer than 512 tokens.

2) The Second method of deriving positional embeddings is using a sinusoidal function. We are construcing a unique positional embedding for each possible position in the Sequence.







