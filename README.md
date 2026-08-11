# Table of contents

1.[Tokenization in LLM](#tokenization-in-llm)
1.[Parameters in LLM](#parameters-in-llm)
1.[Hugging face](#hugging-face)
1.[RAG](#rag)

## tokenization-in-llm
Tokens are the basic building blocks that Large Language Models (LLMs) use to process and generate text. Rather than reading whole words, a model breaks your input into smaller chunks—like subwords or characters—before converting them into numerical vectors to "think" and predict the next output.

eg:
```
                Human Input
                     │
                     ▼
      "The cat sat on the mat."
                     │
                     ▼
           Tokenizer (SentencePiece/BPE)
                     │
                     ▼
    Split into meaningful pieces (tokens)

    ["The", "cat", "sat", "on", "the", "mat", "."]

                     │
                     ▼
        Convert each token to Token IDs

    [517, 2031, 881, 142, 83, 992, 13]

                     │
                     ▼
          Embedding Lookup Table

      517  ─────────► [0.12, -0.45, ... 768 numbers]
      2031 ─────────► [0.87, 0.22, ... 768 numbers]
      ...

                     │
                     ▼
            Transformer Layers
      (Attention + Feed Forward)

                     │
                     ▼
          Predict Next Token ID

                 992 ("mat")

                     │
                     ▼
        Detokenizer converts back

                 "mat"
```

## parameters-in-llm
Parameters are the learned numbers inside a model that store what it has learned during training.
Think of them as millions or billions of tiny adjustable knobs.
During training, the model keeps adjusting these knobs until it becomes good at predicting the next token.

## hugging-face
Hugging face site generally contains all the open source LLM models.  We can download the models and experiment with it.

## rag
Retrieval-Augmented Generation (RAG) is an AI technique that improves large language models by fetching facts from external data sources before writing an answer. Instead of relying only on its fixed training memory, the AI searches a trusted knowledge base or private database to provide accurate, up-to-date responses.
