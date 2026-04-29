# DL-attentions

This repository contains notebook-based experiments for analyzing attention behavior in transformer language models, mainly:

- `DeBERTa_GINI.ipynb`: DeBERTa-v3 MNLI evaluation plus attention/Gini-style analysis.
- `Llama.ipynb`: Llama-family attention analysis.

The project currently uses Jupyter notebooks rather than standalone training/evaluation scripts. The commands below reproduce the notebook outputs by executing the notebooks from top to bottom.

## Repository structure

```text
DL-attentions/
├── DeBERTa_GINI.ipynb    # DeBERTa-v3 MNLI experiment and attention/Gini analysis
├── Llama.ipynb           # Llama-based attention experiment notebook
├── requirements.txt      # Python dependencies
├── README.md             # Project documentation
├── output/
│   ├── Llama/            # Llama notebook outputs
│   └── DeBERTa/          # DeBERTa notebook outputs
```


Install dependencies:

```bash
pip install -r requirements.txt
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

Notes:
- A GPU is recommended for faster model inference, but the notebooks can fall back to CPU if CUDA is not available.
- Some Llama-family checkpoints may require Hugging Face authentication and model access approval.



## License

No license file is currently included. Add a license before distributing or reusing this project publicly.
