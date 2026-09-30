# Decoding Strategies

This project uses a pretrained GPT-2 language model to compare common text-generation decoding strategies. The notebook uses the prompt `The future of artificial intelligence` and shows how decoding choices change the generated continuation.

## Strategies

- **Greedy search** chooses the highest-probability next token at each step.
- **Beam search** keeps several candidate sequences while searching. The notebook uses 5 beams and returns 5 sequences.
- **Top-k sampling** samples from the 50 most likely next tokens.
- **Top-p (nucleus) sampling** samples from the smallest set of tokens whose cumulative probability reaches 0.95.
- **Top-k and top-p sampling** applies both filters, using `top_k=50` and `top_p=0.95`.

The notebook also inspects next-token logits and probabilities. Sampling is seeded with `42` for reproducibility where supported; results can still vary across hardware or library versions.

## Requirements

- Python
- PyTorch
- Transformers
- Jupyter Notebook or JupyterLab

Install the Python dependencies from the project directory:

```bash
python -m pip install -r requirements.txt
```

## Run

Open `notebook.ipynb` in Jupyter or VS Code and run the cells from top to bottom. The notebook automatically selects CUDA when available and otherwise uses the CPU. On the first run, Transformers downloads the GPT-2 model and tokenizer, so an internet connection is required.

## Project Contents

```text
notebook.ipynb       # Walkthrough and generation examples
requirements.txt     # Python package dependencies
results/             # Example outputs for the decoding strategies
```

Generated text is displayed in the notebook's cell outputs. The files in `results/` contain example generations; the notebook does not currently write newly generated text to those files.
