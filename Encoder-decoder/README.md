# Encoder-Decoder Models

Encoder-decoder models also known as Sequence to Sequence Models use both an encoder and a decoder for performing tasks such as Machine Translation, Summarization.
It uses an auto-encoding method to mask the word in the sentence and uses an auto-regressive method to construct the masked word in a sentence
It combines the capabilities of both Auto Encoding and Auto-Regressive to achieve its task.
It uses both left-to-right and right-to-left contexts for predicting the word using span corruption.
Span corruption involves corrupting a span of text in the input sequence and tasking the model with reconstructing the original sequence.

![Context](https://github.com/SharathHebbar/Transformers/blob/main/Encoder-decoder/assets/context.png)

It is also known as the Seq2Seq models
Examples of Sequence to Sequence Model/ Encoder-Decoder models are
T5, BART