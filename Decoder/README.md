# Decoder Only Models

Decoder Only Models also known as Auto Regressive Models uses only a decoder for performing tasks such as Text Generation.
Its task is to predict the next token taking into consideration the text to its left words in a sentence.
In this technique, the next word in a sequence will be generated using information from their preceding words.
It has a Uni-directional context in the sense it takes in the previous word in the sentence and predicts the next word in the sentence.

![Context](https://github.com/SharathHebbar/Transformers/blob/main/Decoder/assets/context.png)

It is also called Causal Language Modelling.
Examples of Causal Language Modelling/ Decoder Only models are
GPT, GPT-2, GPT-3, BLOOM, PaLM