# DL-attentions

DL-attentions is a small research/notebook project for exploring attention behavior in transformer-based natural language inference models. The repository currently contains experiments with DeBERTa and Llama notebooks, using PyTorch, Hugging Face Transformers, Hugging Face Datasets, and visualization libraries.

## Repository Structure

```text
DL-attentions/
├── DeBERTa_GINI.ipynb    # DeBERTa-v3 MNLI experiment and attention/Gini analysis
├── Llama.ipynb           # Llama-based attention experiment notebook
├── requirements.txt      # Python dependencies
└── README.md             # Project documentation
```


Install dependencies:

```bash
pip install -r requirements.txt
```

If `sklearn` causes installation issues, install `scikit-learn` directly:

```bash
pip install scikit-learn
```

## Requirements

The project uses the following main Python packages:

- `numpy`
- `torch`
- `matplotlib`
- `seaborn`
- `datasets`
- `transformers`
- `scikit-learn`

A GPU is recommended for faster model inference, but the notebooks can fall back to CPU if CUDA is not available.

## Usage

Start Jupyter Notebook or JupyterLab:

```bash
jupyter notebook
```

Then open one of the notebooks:

```text
DeBERTa_GINI.ipynb
Llama.ipynb
```

Run the cells from top to bottom. The DeBERTa notebook will automatically select CUDA if available:

```python
device = torch.device("cuda" if torch.cuda.is_available() else "cpu")
```

## Example Workflow

1. Load the tokenizer and transformer model.
2. Load the MNLI validation dataset.
3. Encode premise-hypothesis examples.
4. Run inference and collect predictions.
5. Separate correct and incorrect samples.
6. Extract or inspect attention weights.
7. Compute concentration metrics such as Gini coefficients.
8. Visualize attention patterns.

## Notes

- Some models may require a Hugging Face account or access token, especially Llama-family models.
- Large models can require significant GPU memory.
- Results may vary depending on model version, hardware, and package versions.

## License

No license file is currently included. Add a license before distributing or reusing this project publicly.
