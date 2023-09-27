# Encoder Only Models

- Encoder Only Models also known as Auto Encoding Models uses only an encoder for performing tasks such as Sentiment Analysis, Named Entity Recognition.
- It can be used to mask the word in a sentence.
- Its task is to reconstruct the text by taking into consideration the text to its left and right words in a sentence.
- In this technique, some words are masked, and they are generated using information from their preceding and following words.
- It has a Bi-directional context in the sense it takes in both the previous word in the sentence and the next word in the sentence.

![Context](https://github.com/SharathHebbar/Transformers/blob/main/Encoder/assets/context.png)

- It is also called Masked Language Modelling.
- Examples of Masked Language Modelling / Encoder Only Models are BERT, RoBERTa, DistilBERT

- Code [Fill-Mask](Encoder\fill-mask.ipynb)
- Code [Sentiment-analysis](Encoder\sentiment-analysis.ipynb)