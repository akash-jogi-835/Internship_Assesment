# Neural Language Model Training (PyTorch)

## Project Overview

This project focuses on training a **Neural Language Model (NLM) from
scratch using PyTorch** on the classic novel *Jane Austen's Pride and
Prejudice*.\
The objective is to demonstrate a clear understanding of **model
capacity, training dynamics, and generalization** by implementing and
comparing three distinct training scenarios:

-   **Underfitting**
-   **Overfitting**
-   **Best Fit**

No pre-trained models or high-level NLP libraries were used; all
components were implemented manually.

------------------------------------------------------------------------

## Dataset

-   **Source:** `Pride_and_Prejudice-Jane_Austen.txt` (provided)
-   **Link :** https://drive.google.com/drive/folders/1_yd3M0figTNBDlTRG48NbHG9h0TfJswi?usp=sharing
-   **Type:** Plain text (word-level language modeling)

### Preprocessing Steps

-   Custom word-level tokenization
-   Vocabulary creation and word-to-index mapping
-   Sequence batching using `torch.utils.data.Dataset` and `DataLoader`

------------------------------------------------------------------------

## Model Architecture

The language model is a **custom LSTM-based Neural Language Model**,
implemented entirely from scratch.

### Key Components

-   Embedding Layer
-   Multi-layer LSTM
-   Fully Connected Linear Layer for next-word prediction

### Evaluation Metric

-   **Perplexity (PPL)** --- primary metric for evaluating language
    model performance

------------------------------------------------------------------------

## Experimental Results

Three training configurations were evaluated to illustrate different
model behaviors:

 | Scenario | Train Loss | Val Loss | Train PPL | Val PPL | Interpretation |
|---------|------------|----------|-----------|---------|----------------|
| Underfit | 4.6379 | 4.6899 | – | 108.84 | Model too small |
| Overfit | 2.9018 | 2.0058 | 18.21 | 7.43 | Memorization |
| Best Fit | 0.3513 | 0.3771 | 1.42 | 1.46 | Optimal generalization |

------------------------------------------------------------------------

## Setup and Installation

### Clone the Repository

``` bash
git clone [<your-repo-link>](https://github.com/akash-jogi-835/Internship_Assesment)
cd Internship_Assesment
```

### Install Dependencies

``` bash
pip install torch numpy matplotlib
```

### Dataset Setup

-   Place `Pride_and_Prejudice-Jane_Austen.txt` in the specified data
    directory\
    **OR**
-   Mount Google Drive if using Google Colab (as described in the
    notebook)

------------------------------------------------------------------------

## How to Run Training

To ensure reproducibility, **random seed = 42** has been fixed.

1.  Open the provided **Google Colab / Jupyter Notebook**
2.  Execute the cells sequentially
3.  The notebook will automatically:
    -   Train **Underfit**, **Overfit**, and **Best Fit** models
    -   Generate training and validation loss plots
    -   Compute perplexity for each scenario

------------------------------------------------------------------------

## Deliverables

-   `model_implementation.py` --- Core PyTorch model definition\
-   `training_script.ipynb` --- Training, evaluation, and plotting
    logic\
-   `Report.pdf` --- Concise summary of methodology and results\
-   `plots/` --- Loss and perplexity curves for all three scenarios

------------------------------------------------------------------------

## Conclusion

This project demonstrates how **model capacity and training duration**
directly influence language model performance.\
The **Best Fit** configuration achieves strong generalization with
minimal loss gap, validating perplexity as an effective metric for
neural language modeling.

------------------------------------------------------------------------

*Implemented entirely using PyTorch for educational and experimental
purposes.*
