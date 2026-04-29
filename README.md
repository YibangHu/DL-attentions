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

## Project Goals

This project investigates how attention is distributed inside deep language models. The notebooks are designed to:

- run transformer models on natural language inference data,
- inspect attention patterns from model layers/heads,
- compute statistics such as Gini-style concentration measures,
- visualize attention behavior with plots and heatmaps,
- compare attention behavior across model families such as DeBERTa and Llama.

## Main Notebooks

### `DeBERTa_GINI.ipynb`

This notebook uses a DeBERTa-v3 model for MNLI-style natural language inference. It loads the `nyu-mll/glue` MNLI validation split, tokenizes premise-hypothesis pairs, runs inference, and supports analysis of model attention distributions.

Expected components include:

- loading `MoritzLaurer/DeBERTa-v3-base-mnli`,
- evaluating predictions on MNLI validation examples,
- collecting correct and incorrect predictions,
- analyzing attention behavior,
- plotting attention/Gini-related visualizations.

### `Llama.ipynb`

This notebook is intended for Llama-based attention analysis. It can be used to inspect attention behavior in an autoregressive large language model and compare it with encoder-style models such as DeBERTa.

## Installation

Clone the repository:

```bash
git clone https://github.com/YibangHu/DL-attentions.git
cd DL-attentions
```

Create and activate a virtual environment:

```bash
python -m venv .venv
source .venv/bin/activate      # macOS/Linux
# .venv\Scripts\activate       # Windows
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
