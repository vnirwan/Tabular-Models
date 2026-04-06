# TabPFN: Embeddings vs One-Hot Encoding

## Overview

This repository explores a key hypothesis inspired by the whitepaper:
**"Developing Foundation Models for Real-World Tabular Data"** fileciteturn0file0

> *Categorical embeddings can significantly outperform one-hot encoding by reducing sample complexity and capturing semantic relationships between categories.*

The goal of this project is to **empirically validate** this claim using **TabPFN**, a state-of-the-art tabular foundation model.

---

## Motivation

Traditional tabular ML approaches treat categorical variables as independent (e.g., one-hot encoding). However, the whitepaper argues that:
Paper link: https://fundamental.tech/whitepaper.pdf

- One-hot encoding ignores relationships between categories
- Embeddings capture semantic similarity (e.g., "Paris" closer to "London" than "Banana")
- This leads to **dramatic improvements in sample efficiency**

Theoretical results suggest that embeddings can reduce sample complexity by **orders of magnitude** in high-cardinality settings.

---

## Experiments

### 1. Integer Encoding vs Embeddings (Attempt 2)
- File: `Integer encode vs embedding.ipynb`
- Compares raw integer encoding vs learned embeddings
- Tests whether TabPFN can benefit from embedding-based representations

### 2. One-Hot Encoding vs Embeddings (Attempt 3)
- File: `One-Hot vs Embedding.ipynb`
- Direct comparison between:
  - One-hot encoding
  - Learned embeddings
- Focus: performance differences under realistic tabular settings

---

## Key Result (So Far)

✅ **Embeddings outperform one-hot encoding**

This aligns with the theoretical claim from the paper that:
- Embeddings exploit structure in categorical data
- One-hot representations scale poorly with cardinality

---

## Why This Matters

This work supports a broader shift in tabular ML:

| Traditional ML | Emerging Approach |
|---------------|------------------|
| Feature engineering | Representation learning |
| One-hot encoding | Learned embeddings |
| Task-specific models | Foundation models |

If validated further, this could change how we approach:
- Feature preprocessing
- Model design
- Data efficiency in real-world ML systems

---

## Work in Progress

This repository is **ongoing work**. Next steps include:

- [ ] Reproducing results across multiple datasets
- [ ] Testing robustness to noise and data size
- [ ] Validating additional corollaries from the whitepaper
- [ ] Comparing against tree-based baselines (XGBoost, CatBoost)
- [ ] Exploring hybrid approaches (embeddings + TabPFN + LLM signals)

---

## How to Run

1. Clone the repo
2. Install dependencies (e.g., TabPFN, numpy, pandas, sklearn)
3. Run notebooks:
   ```bash
   jupyter notebook Integer encode vs embedding.ipynb
   ```

---

## References

- Garnelo & Czarnecki, *Developing Foundation Models for Real-World Tabular Data* fileciteturn0file0
- TabPFN: Prior-Data Fitted Networks for Tabular Data

---

## Contributions

This is an exploratory research repo. Feedback, ideas, and collaborations are welcome!


