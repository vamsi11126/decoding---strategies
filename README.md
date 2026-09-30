"""
This notebook explores different decoding strategies for text generation using a pre-trained `gpt2` model from the `transformers` library. It demonstrates how various methods, such as greedy search, beam search, Top-K sampling, and Top-P (nucleus) sampling, lead to different generated outputs for the same initial prompt.

### Decoding Strategies Covered:

*   **Greedy Search**: Selects the token with the highest probability at each step.
*   **Beam Search**: Explores multiple high-probability paths simultaneously, aiming for a globally better sequence.
*   **Top-K Sampling**: Selects the next token randomly from the top `k` most probable tokens.
*   **Top-P (Nucleus) Sampling**: Selects the next token randomly from the smallest set of tokens whose cumulative probability exceeds a threshold `p`.
*   **Combination (Top-K and Top-P) Sampling**: Combines both Top-K and Top-P filtering.

### Results:

The generated text for each decoding strategy is saved to individual `.txt` files within the `results/` directory:

*   `results/greedy.txt`
*   `results/beam.txt`
*   `results/top_k.txt`
*   `results/top_p.txt`
"""