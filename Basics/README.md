# Basics of Transformers

# Codes

1. Tokenizer using ```BERT```
2. Embeddings using ```BERT```
3. Semantic Similarity between sentences using ```BERT```
4. Extractive Question and Answer using ```Bi-directional Encoder Representation Transformer```
5. Instruction following using ```Generative Pre-trained Transformer```
6. Product Reviews using ```Text To Text Transfer Transformer```

<hr>

# BERT (Bi-directional Encoder Representation Transformers)

## Abbreviation

- Bi-directional: Reads text in both left and right directions, better context
- Encoder: Encoder Only Architecture
- Representation: Creates meaningful word representation
- Transformer: Based on Transformer Architecture

## Overview

- Encoder Only model
- Stacked Encoders
- Bi-directional contexts

## Tasks

1. Masked Language Modelling (MLM)
    - Randomly maskees words in a sentence 
    - BERT's task is to predict masked words using context
    - The outcome is to learn word relationships and context understanding

2. Next Sentence Prediction (NSP)
    - Focus on learning sentence relationship
    - BERT's task is to determine if second sentence follows first naturally

Example:

- Here the Sentence A follows Sentence B
    - Sentence A: I bought a mobile phone
    - Sentence B: There was a sale for mobile phones

## Use Cases

1. Text Classification
2. Named Entity Recognition
3. Extractive Question Answering
4. Semantic Similarity

<hr>

# GPT (Generative Pre-trained Transformers)

## Abbreviation

- Generative: It generates text
- Pre-trained: As it is pre-trained
- Transformer: Based on Transformer Architecture

## Overview

- Coherent and contextually relevant text
- Decoder Only
- Stacked Decoder
- Unidirectional Provisioning

## Tasks

1. Causal Language Modelling (CLM)
    - Predicts next word in a sentence 
    - GPT's task is to predict next word in a sentence

## Use Cases

1. Text Generation
2. Machine Translation
3. Summarization

<hr>

# T5 (Text To Text Transfer Transformers)

## Abbreviation

- Text To Text (Text2Text): The input and output of the model will be text
- Transfer: T5 transfers pre-training knowledge to various tasks (kind of foundational model) 
- Transformer: Based on Transformer Architecture

## Overview

- Flexible and Adaptable
- Encoder and Decoder
- Text to text approach
- Task specific prefixes

1. Based on original Transformers architecture
2. Blending BERT's and GPT's pre-training approaches
3. Unifying BERT's objective to predict missing words with valuable context
4. Incorporating GPT's <b>AutoRegressive</b> generation for fluent multi-word output 

## Tasks

1. Fill in the blank Text Generation
    - Corrupt pieces of a sentence
    - T5's task is to fill in the gaps to match the context
    - The outcome is to learn word relationships and context understanding

- Task specific prefixes: "Can you convert this text to French language: Hello, How are you"

## Use Cases

1. Machine Translation
2. Keyword Generation
3. Summarization
4. Abstractive Question Answering

<hr>

