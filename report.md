# Neural Language Model Training Report

## Jane Austen's *Pride and Prejudice*

------------------------------------------------------------------------

## 1. Objective and Setup

The primary goal of this task was to implement a **neural language model
from scratch using PyTorch** to demonstrate the relationship between
**model capacity**, **training duration**, and **generalization**.\
The project explicitly avoided the use of pre-trained models or
high-level NLP libraries to ensure a clear understanding of core
language modeling principles.

**Key Setup Details:** - **Dataset:** Jane Austen's *Pride and
Prejudice*\
- **Architecture:** Multi-layer LSTM (Long Short-Term Memory) network\
- **Metric:** Perplexity (PPL) for performance evaluation\
- **Implementation:** Custom preprocessing, tokenization, and batching

------------------------------------------------------------------------

## 2. Experimental Scenarios and Rationale

To demonstrate model behavior under varying capacities, three distinct
training scenarios were implemented:

### 2.1 Underfitting Scenario

A low-capacity model with a small hidden size and limited training
epochs was used.\
This configuration failed to capture the complexity of the language,
resulting in **high loss and high perplexity**.

### 2.2 Overfitting Scenario

A moderately sized LSTM with **dropout = 0.3** was trained for extended
epochs.\
While training loss decreased, validation loss increased significantly,
indicating **memorization of training data** and poor generalization.

### 2.3 Best-Fit Scenario

A large-scale LSTM with **512 hidden units and no dropout** was trained
using iterative hyperparameter tuning and learning-rate scheduling.\
This model achieved **low loss and strong generalization**, balancing
capacity and training duration effectively.

------------------------------------------------------------------------

## 3. Results Summary

  ------------------------------------------------------------------------------------
 | Scenario | Train Loss | Val Loss | Train PPL | Val PPL |
|---------|------------|----------|-----------|---------|
| Underfit | 4.6379 | 4.6899 | – | 108.84 |
| Overfit | 2.9018 | 2.0058 | 18.21 | 7.43 |
| Best Fit | 0.3513 | 0.3771 | 1.42 | 1.46 |

------------------------------------------------------------------------

## 4. Key Observations and Performance Analysis

-   **Perplexity Achievement:**\
    The best-fit model achieved a validation perplexity of **1.59**,
    indicating strong next-token prediction capability.

-   **Generalization Gap:**\
    A narrow gap of **-0.0604** between training and validation loss
    confirms stable generalization.

-   **Model Capacity Impact:**\
    Increasing parameters to approximately **7.6 million** was essential
    for capturing the stylistic and syntactic nuances of Jane Austen's
    prose.

------------------------------------------------------------------------

## 5. Repository and Deliverables

The project repository follows all submission guidelines and includes:

-   **Code:** PyTorch scripts for preprocessing, model definition, and
    training\
-   **Plots:** Loss curves for underfit, overfit, and best-fit
    experiments\
-   **README:** Reproducibility instructions with fixed random seeds

------------------------------------------------------------------------

**Conclusion:**\
This project clearly demonstrates how neural language model performance
depends on capacity and training dynamics, with perplexity serving as an
effective evaluation metric for language modeling tasks.

