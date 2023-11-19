# Background

## Transformers v/s LSTM

<table>

<tr>
<th>Aspects</th>
<th>LSTM</th>
<th>Transformers</th>
</tr>

<tr>
<td>Processing Methods</td>
<td>Sequential (processess one token at a time)</td>
<td>Parallel (processes all tokens simultaneously)</td>
</tr>

<tr>
<td>Handling Dependencies</td>
<td>Can struggle with long-term dependencies</td>
<td>Excels at capturing long-term dependencies</td>
</tr>

<tr>
<td>Attention Mechanism</td>
<td>No inherent attention, can be added separately</td>
<td>Inherent multi-headed self-attention mechanism</td>
</tr>

<tr>
<td>Efficiency and Scalability</td>
<td>Less efficient and scalable for very long sequences</td>
<td>More efficient and scalable for long sequences and large datasets</td>
</tr>

</table>

## Components

The transformers architecture is made up of
1. **Input Embeddings**: Converts the input tokens into continuous vectors that the model can work with.
2. **Encoder**: Consists of multiple layers, each containing a self attention mechanism and a feed forward neural network, which process input text.
3. **Decoder**: It also has multiple layers each containing a self attention mechanism, an encoder-decoder attention mechanism and a feed forward neural network, which generate the output text.
4. **Self-Attention mechanism**: Helps the model understand the relationship between words in a sentence, even if they're far apart.
5. **Positional Encoding**: Added to the input embeddings to give the model a sense of word order in the sequence.
6. **Layer Normalization**: A technique used within the encoder and decoder layers to help stabilise the training process.
7. **Residual Connection**: Used in the encoder and decoder layers to help with gradient flow during training and mitigate the vanishing gradient problem.
8. **Encoder-Decoder attention mechanism**: Used in the decoder to help it focus on relevant parts of the input when generating output.
9. **Output Linear Layer**: Converts the decoder's output into logits for each token in the target vocabulary.
10. **Softmax Layer**: Applied to the logits to produce probabilities for each token in the target vocabulary.

## Explanation
1. **Self Attention**: Enables the model to weigh the importance of word-pairs relative to one another and understand relationships between words.
2. **Scaled dot-product attention**: Computes attention scores between words in a sequence throught dot products, scaling and softmax.
3. **Multi-head attention**: Employs multiple heads to simultaneously capture different aspects of input data such as syntactic and semantic realtionships for a more comprehensive understanding.
4. **Positional Encoding**: It provides information about position of words. It involves adding unique, learnable vectors to the input embeddings, allowing the model to recognize the order of words and understand the structure of the sentence.
5. **Feed Forward Neural Network**: It learns complex, non-linear relationship between input embeddings and their context.
6. **Layer Normalization**: It results in improved training stability and faster convergence.
7. **Encoder**: It procesess input text into a continuous representation that captures word relationships and context.
8. **Decoder**: It is used to generate next word in the sentence.

## Attention Mechanism 

- Score Calculation: score(Q, K) = QK<sup>T</sup>
- Softmax Normalization: softmax(x<sub>i</sub>) = exp(x<sub>i</sub>) / Σ exp(x<sub>j</sub>)
- Weighted Sum: Attention(Q, K, V) = softmax(QK<sup>T</sup>)V

## Multi-Headed Attention

## Positional Encoding

## Parameter Sharing