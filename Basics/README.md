# Basics of Transformers

# BERT (Bi-directional Encoder Representation Transformers)

## Abbreviation

- Bi-directional: Reads text in both left and right directions, better context
- Encoder: Encoder Only Architecture
- Representation: Creates meaningful word representation
- Transformer: Based on Transformer Architecture

## Tasks

1. Masked Language Modelling (MLM)
1.1 Randomly maskees words in a sentence 
1.2 BERT's task is to predict masked words using context
1.3 The outcome is to learn word relationships and context understanding

2. Next Sentence Prediction (NSP)
2.1 Focus on learning sentence relationship
2.2 BERT's task is to determine if second sentence follows first naturally

Example:

- Here the Sentence A follows Sentence B
Sentence A: I bought a mobile phone
Sentence B: There was a sale for mobile phones

## Use Cases
1. Text Classification
2. Named Entity Recognition
3. Extractive Question Answering
4. Semantic Similarity

<hr>

# Codes
1. Tokenizer
2. Embeddings
3. Semantic Similarity between sentences using BERT
4. Extractive Question and Answer using Bi-directional Encoder Representation Transformer
5. Instruction following using Generative Pre-trained Transformer
6. Product Reviews using Text To Text Transfer Transformer