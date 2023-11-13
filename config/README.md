# Hyperparameters

## Important Hyperparameters to watch out

1. Temperature: - ```temperature```

It controls the degree of randomness in token selection. Lower the temperattures are good for prompts that expect a true or correct response, while higher temperatures can lead to more diverse or unexpected results. With a temperature of 0 the highest probability token is always selected. For most use cases, try starting with a temperature of 0.2.

2. Token Limit: - ```max_new_tokens```

It determines the maximum amount of text output from one prompt.

3. Top-k: - ```top_k```

It changes how the model selects tokens from output. A top-k of 1 means the selected token is most probable among all tokens in the model's vocabulary (also called as greedy decoding), while a top-k of 3 means that the next token is selected from among the 3 most probable tokens (using temperature).

4. Top-p: ```top_p```

It changes how the model selects tokens for output. Tokens are selected from most probable to least until the sum of their probabilities equals to top-p value. For example, if tokens A, B and C have a probability of 0.3, 0.2 and 0.1 and the top-p value is 0.5, then the model will select either A or B as the next token (using temperature).

5. Stop Sequence:

A stop sequence is a series of characters that stops the response generation if the model encounters it. The sequence is not included as a part of the response.

6. Block Abusive Words:

Adjusts how likely you are to see reponses that could be harmful. Model responses are blocked based on the probability that it contains violent, sexual, toxic or derogatory content.

7. Return response:

The maximum number of model responses generated per prompt. Responses can still be blocked due to safety filters.

**Note: All those parameters cannot be applied to all the models make sure to do your research before trying out with the hyperparameters.**

## Parameters that can control the length of output

- ```max_length``` (int, optional, defaults to 20) — The maximum length the generated tokens can have. Corresponds to the length of the input prompt + max_new_tokens. Its effect is overridden by max_new_tokens, if also set.
- ```max_new_tokens``` (int, optional) — The maximum numbers of tokens to generate, ignoring the number of tokens in the prompt.
- ```min_length``` (int, optional, defaults to 0) — The minimum length of the sequence to be generated. Corresponds to the length of the input prompt + min_new_tokens. Its effect is overridden by min_new_tokens, if also set.
- ```min_new_tokens``` (int, optional) — The minimum numbers of tokens to generate, ignoring the number of tokens in the prompt.
- ```early_stopping``` (bool or str, optional, defaults to False) — Controls the stopping condition for beam-based methods, like beam-search. It accepts the following values: True, where the generation stops as soon as there are num_beams complete candidates; False, where an heuristic is applied and the generation stops when is it very unlikely to find better candidates; "never", where the beam search procedure only stops when there cannot be better candidates (canonical beam search algorithm).


## Parameters that can control the generation strategy used

- ```do_sample``` (bool, optional, defaults to False) — Whether or not to use sampling ; use greedy decoding otherwise.
- ```num_beams``` (int, optional, defaults to 1) — Number of beams for beam search. 1 means no beam search.
- ```num_beam_groups``` (int, optional, defaults to 1) — Number of groups to divide num_beams into in order to ensure diversity among different groups of beams. this paper for more details.
- ```penalty_alpha``` (float, optional) — The values balance the model confidence and the degeneration penalty in contrastive search decoding.
- ```use_cache``` (bool, optional, defaults to True) — Whether or not the model should use the past last key/values attentions (if applicable to the model) to speed up decoding.


## Parameters for manipulation of the model output logits

- ```temperature``` (float, optional, defaults to 1.0) — The value used to modulate the next token probabilities.
- ```top_k``` (int, optional, defaults to 50) — The number of highest probability vocabulary tokens to keep for top-k-filtering.
- ```top_p``` (float, optional, defaults to 1.0) — If set to float < 1, only the smallest set of most probable tokens with probabilities that add up to top_p or higher are kept for generation.
- ```typical_p``` (float, optional, defaults to 1.0) — Local typicality measures how similar the conditional probability of predicting a target token next is to the expected conditional probability of predicting a random token next, given the partial text already generated. If set to float < 1, the smallest set of the most locally typical tokens with probabilities that add up to typical_p or higher are kept for generation. See this paper for more details.
- ```epsilon_cutoff``` (float, optional, defaults to 0.0) — If set to float strictly between 0 and 1, only tokens with a conditional probability greater than epsilon_cutoff will be sampled. In the paper, suggested values range from 3e-4 to 9e-4, depending on the size of the model. See Truncation Sampling as Language Model Desmoothing for more details.
- ```eta_cutoff``` (float, optional, defaults to 0.0) — Eta sampling is a hybrid of locally typical sampling and epsilon sampling. If set to float strictly between 0 and 1, a token is only considered if it is greater than either eta_cutoff or sqrt(eta_cutoff) * exp(-entropy(softmax(next_token_logits))). The latter term is intuitively the expected next token probability, scaled by sqrt(eta_cutoff). In the paper, suggested values range from 3e-4 to 2e-3, depending on the size of the model. See Truncation Sampling as Language Model Desmoothing for more details.
- ```diversity_penalty``` (float, optional, defaults to 0.0) — This value is subtracted from a beam’s score if it generates a token same as any beam from other group at a particular time. Note that diversity_penalty is only effective if group beam search is enabled.
- ```repetition_penalty``` (float, optional, defaults to 1.0) — The parameter for repetition penalty. 1.0 means no penalty. See this paper for more details.
- ```encoder_repetition_penalty``` (float, optional, defaults to 1.0) — The paramater for encoder_repetition_penalty. An exponential penalty on sequences that are not in the original input. 1.0 means no penalty.
- ```length_penalty``` (float, optional, defaults to 1.0) — Exponential penalty to the length that is used with beam-based generation. It is applied as an exponent to the sequence length, which in turn is used to divide the score of the sequence. Since the score is the log likelihood of the sequence (i.e. negative), length_penalty > 0.0 promotes longer sequences, while length_penalty < 0.0 encourages shorter sequences.
- ```no_repeat_ngram_size``` (int, optional, defaults to 0) — If set to int > 0, all ngrams of that size can only occur once.
- ```bad_words_ids```(List[List[int]], optional) — List of list of token ids that are not allowed to be generated. Check NoBadWordsLogitsProcessor for further documentation and examples.
- ```force_words_ids```(List[List[int]] or List[List[List[int]]], optional) — List of token ids that must be generated. If given a List[List[int]], this is treated as a simple list of words that must be included, the opposite to bad_words_ids. If given List[List[List[int]]], this triggers a disjunctive constraint, where one can allow different forms of each word.
- ```renormalize_logits``` (bool, optional, defaults to False) — Whether to renormalize the logits after applying all the logits processors or warpers (including the custom ones). It’s highly recommended to set this flag to True as the search algorithms suppose the score logits are normalized but some logit processors or warpers break the normalization.
- ```constraints``` (List[Constraint], optional) — Custom constraints that can be added to the generation to ensure that the output will contain the use of certain tokens as defined by Constraint objects, in the most sensible way possible.
- ```low_memory``` (bool, optional) — Switch to sequential topk for contrastive search to reduce peak memory. Used with contrastive search.

## Parameters that define the output variables of `generate`

- ```num_return_sequences```(int, optional, defaults to 1) — The number of independently computed returned sequences for each element in the batch.
- ```output_attentions``` (bool, optional, defaults to False) — Whether or not to return the attentions tensors of all attention layers. See attentions under returned tensors for more details.
- ```output_hidden_states``` (bool, optional, defaults to False) — Whether or not to return the hidden states of all layers. See hidden_states under returned tensors for more details.
- ```output_scores``` (bool, optional, defaults to False) — Whether or not to return the prediction scores. See scores under returned tensors for more details.
- ```return_dict_in_generate``` (bool, optional, defaults to False) — Whether or not to return a ModelOutput instead of a plain tuple.

## Special tokens that can be used at generation time

- ```pad_token_id``` (int, optional) — The id of the padding token.
- ```bos_token_id``` (int, optional) — The id of the beginning-of-sequence token.
- ```eos_token_id``` (Union[int, List[int]], optional) — The id of the end-of-sequence token. Optionally, use a list to set multiple end-of-sequence tokens.

## Generation parameters exclusive to encoder-decoder models

- ```encoder_no_repeat_ngram_size``` (int, optional, defaults to 0) — If set to int > 0, all ngrams of that size that occur in the encoder_input_ids cannot occur in the decoder_input_ids.
- ```decoder_start_token_id``` (int, optional) — If an encoder-decoder model starts decoding with a different token than bos, the id of that token.


Link for further research: [HuggingFace](https://huggingface.co/docs/transformers/main_classes/text_generation)