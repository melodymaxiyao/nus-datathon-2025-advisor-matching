# NUS Datathon 2025 — Financial Advisor Matching & Ranking

**3rd Place, Advanced Category | NUS Datathon 2025**

This project develops a data-driven recommendation system for matching clients with suitable financial advisors, with the objective of improving policy conversion, customer satisfaction, and operational efficiency.

## Problem

The task is to recommend suitable financial advisors to clients using agent profiles, client characteristics, and historical policy information.

The main challenges include high-dimensional mixed-type data, a large advisor pool, the absence of explicit negative matches, and the lack of a direct benchmark for match quality.

## Methodology

Our primary solution uses a three-stage machine-learning pipeline:

### 1. Agent Clustering
- **Multiple Correspondence Analysis (MCA)** for dimensionality reduction
- **Gaussian Mixture Model (GMM)** for probabilistic clustering of financial advisors

### 2. Client-to-Cluster Classification
- **Random Forest** to predict the advisor cluster most suitable for each client

### 3. Advisor Ranking
- **XGBoost Ranker** to rank advisors within the predicted cluster
- Ranking incorporates historical conversion performance, policy in-force information, and matching features

The project also explored a second representation-learning approach using cosine-similarity matching, Transformer-based agent/client embeddings, and contrastive learning.

## Evaluation

The primary pipeline is evaluated separately at each stage:

| Stage | Metrics |
| --- | --- |
| Clustering | Silhouette Score, Davies–Bouldin Index, Log-Likelihood |
| Classification | Accuracy, Precision, Recall, F1-score |
| Ranking | NDCG@5, MRR |

Key reported results include:

- **Classification Accuracy:** 80.67%
- **F1-score:** 79.37%
- **NDCG@5:** 1.0
- **MRR:** 0.0033

The results indicate strong classification performance and high top-five ranking quality, while the clustering stage leaves room for improvement.

## Key Takeaway

The project decomposes financial-advisor recommendation into interpretable **clustering → classification → ranking** stages rather than treating it as a single black-box prediction problem.

This structure provides a scalable and business-oriented framework for matching clients with advisors while retaining model interpretability.

## Presentation

The competition presentation is available here:

[`NUS_Datathon_2025.pdf`](NUS_Datathon_2025.pdf)

## Team

Zheyuan Lai · Yuxin Liu · Jingyu Shi · Xiyao Ma · Yuhan Wang  
National University of Singapore
