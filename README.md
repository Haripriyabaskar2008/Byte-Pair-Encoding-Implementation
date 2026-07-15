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
learning Outcome:
Through this project, the complete working process of the Byte Pair Encoding algorithm was implemented and understood, including vocabulary learning, subword tokenization, and encoding/decoding of words. This project provides a strong foundation for understanding tokenization techniques used in modern Large Language Models (LLMs).
👩‍💻 Author
     Hari Priya.B
     B.Sc. Computer Science with Artificial Intelligence
**
⭐ This project was developed for educational purposes as part of a Large Language Models (LLMs) course to understand the Byte Pair Encoding (BPE) algorithm from scratch.**
