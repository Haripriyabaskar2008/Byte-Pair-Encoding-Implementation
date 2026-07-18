** Byte-Pair-Encoding-Implementation**
Project Overview:

     This project implements the **Byte Pair Encoding (BPE)** algorithm from scratch using **Python** and **NumPy** without relying on any external tokenization libraries. BPE is a widely used subword tokenization technique in Large Language Models (LLMs) that learns a vocabulary by repeatedly merging the most frequent adjacent symbol pairs.
This implementation demonstrates the complete BPE workflow, including corpus preprocessing, vocabulary construction, pair frequency analysis, merge rule generation, and token encoding/decoding.
Objective

The objective of this project is to understand and implement the Byte Pair Encoding (BPE) algorithm from scratch by:

          - Reading and preprocessing a text corpus
          - Splitting words into character-level tokens
          - Counting word and pair frequencies
          - Learning merge rules through iterative pair merging
          - Building a subword vocabulary
          - Implementing custom `encode()` and `decode()` functions
          - Demonstrating the complete tokenization process without external BPE libraries.
          Features

Read text corpus from a file:
- Text preprocessing
- Character-level tokenization
- End-of-word (`</w>`) symbol handling
- Word frequency calculation
- Adjacent symbol pair counting
- Most frequent pair selection
- Pair merging
- Vocabulary update
- Merge rule generation
- Final vocabulary construction
- Custom `encode()` function
- Custom `decode()` function
- Sample tokenizer testing.
- Project Structure


Custom-BPE-Tokenizer/
│
├── corpus.txt
├── BPE_From_Scratch.ipynb
├── README.md
Technologies Used:
     - Python 3
     - NumPy
     - JupyterLab
🔄 Algorithm Workflow:

```text
                ┌───────────────┐
                │     Start     │
                └───────┬───────┘
                        │
                        ▼
          ┌─────────────────────────┐
          │ Read corpus.txt file    │
          └──────────┬──────────────┘
                     │
                     ▼
          ┌─────────────────────────┐
          │ Preprocess the Text     │
          │ (Lowercase & Clean)     │
          └──────────┬──────────────┘
                     │
                     ▼
          ┌─────────────────────────┐
          │ Split Words into        │
          │ Characters + </w>       │
          └──────────┬──────────────┘
                     │
                     ▼
          ┌─────────────────────────┐
          │ Count Word Frequencies  │
          └──────────┬──────────────┘
                     │
                     ▼
          ┌─────────────────────────┐
          │ Find Adjacent Symbol    │
          │ Pairs                   │
          └──────────┬──────────────┘
                     │
                     ▼
          ┌─────────────────────────┐
          │ Count Pair Frequencies  │
          └──────────┬──────────────┘
                     │
                     ▼
          ┌─────────────────────────┐
          │ Select Most Frequent    │
          │ Pair                    │
          └──────────┬──────────────┘
                     │
                     ▼
          ┌─────────────────────────┐
          │ Merge Selected Pair     │
          └──────────┬──────────────┘
                     │
                     ▼
          ┌─────────────────────────┐
          │ Update Vocabulary       │
          └──────────┬──────────────┘
                     │
                     ▼
          ┌─────────────────────────┐
          │ Repeat Until Required   │
          │ Number of Merges        │
          └──────────┬──────────────┘
                     │
                     ▼
          ┌─────────────────────────┐
          │ Store Merge Rules       │
          └──────────┬──────────────┘
                     │
                     ▼
          ┌─────────────────────────┐
          │ Build Final Vocabulary  │
          └──────────┬──────────────┘
                     │
                     ▼
          ┌─────────────────────────┐
          │ Encode New Words        │
          └──────────┬──────────────┘
                     │
                     ▼
          ┌─────────────────────────┐
          │ Decode Tokens           │
          └──────────┬──────────────┘
                     │
                     ▼
                ┌───────────────┐
                │      End      │
                └───────────────┘
```
 🔄 Algorithm Workflow:
flowchart TD
    A([Start])
    B[Read corpus.txt]
    C[Preprocess Text]
    D[Split Words into Characters + </w>]
    E[Count Word Frequencies]
    F[Find Adjacent Symbol Pairs]
    G[Count Pair Frequencies]
    H[Select Most Frequent Pair]
    I[Merge Selected Pair]
    J[Update Vocabulary]
    K{More Merges?}
    L[Store Merge Rules]
    M[Build Final Vocabulary]
    N[Encode New Words]
    O[Decode Tokens]
    P([End])

    A --> B
    B --> C
    C --> D
    D --> E
    E --> F
    F --> G
    G --> H
    H --> I
    I --> J
    J --> K
    K -- Yes --> F
    K -- No --> L
    L --> M
    M --> N
    N --> O
    O --> P
```
learning Outcome:
Through this project, the complete working process of the Byte Pair Encoding algorithm was implemented and understood, including vocabulary learning, subword tokenization, and encoding/decoding of words. This project provides a strong foundation for understanding tokenization techniques used in modern Large Language Models (LLMs).




                                Autoregressive Causal Language Model
Project Overview:
This project implements the basic pipeline of an Autoregressive Causal Language Model (ARLM) using Python and NumPy. The model predicts the next token in a sequence based only on previously seen tokens and does not access future tokens during prediction.
The project demonstrates how the BPE tokenizer connects with an autoregressive language model. The text is first converted into token IDs, which are then processed through embeddings, positional encoding, causal masking, self-attention, a linear layer, and softmax to generate the next-token prediction.
This implementation is designed for educational purposes to understand the fundamental concepts behind Causal Language Models and Transformer-based architectures
Objective

The objective of this project is to understand and implement the basic working pipeline of an autoregressive causal language model by:

-Converting text into token IDs using a tokenizer
-Creating input-target training pairs
-Representing tokens using embedding vectors
-Adding positional information
-Applying a causal mask to prevent access to future tokens
-Computing self-attention
-Generating vocabulary logits using a linear layer
-Applying softmax for probability distribution
-Calculating cross-entropy loss
-Predicting the next token
-Demonstrating basic text generation.
                                 Algorithm Workflow:
                    ┌─────────────────────┐
                    │        START        │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   Collect Raw Text  │
                    │      Corpus         │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   BPE Tokenizer     │
                    │  (Subword Tokens)   │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │ Convert Tokens into │
                    │     Token IDs       │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │ Create Input-Target │
                    │       Pairs         │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │  Token Embedding    │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │ Positional Encoding│
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │    Causal Mask      │
                    │ (Block Future Info) │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   Self-Attention    │
                    │   Q, K and V        │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │    Linear Layer     │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │       Logits        │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │      Softmax        │
                    │ Probability Scores  │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │  Next Token         │
                    │    Prediction       │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │ Cross-Entropy Loss  │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   Backpropagation   │
                    │  Update Parameters  │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │  Generate Next      │
                    │      Token          │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │  Repeat Generation  │
                    │  Until Completion   │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │         END         │
                    └─────────────────────┘
Learning Outcomes:
Through this project, the fundamental workflow of an autoregressive causal language model was implemented and explored. The project demonstrates how tokenized text is transformed into embeddings, processed using positional information and causal self-attention, and finally used to predict the next token.
This implementation provides a basic understanding of the core concepts behind Causal Language Models and Transformer-based Large Language Models (LLMs).

👩‍💻 Author
     Hari Priya.B
     B.Sc. Computer Science with Artificial Intelligence
**
⭐ This project was developed for educational purposes as part of a Large Language Models (LLMs) course to understand the Byte Pair Encoding (BPE) algorithm from scratch.**
