# ZOMATHON'26

# 🍽 Cart Super Add-On (CSAO) Intelligent Recommendation System  
### Hybrid Sequential Ranking with Semantic AI Edge & Cold Start Robustness  

---

## 📌 Problem Statement

Design a production-ready Cart Super Add-On (CSAO) recommendation system that dynamically suggests relevant complementary items during checkout to maximize add-on acceptance and Average Order Value (AOV), while maintaining low latency and robustness to cold-start scenarios.

---

## 🚀 Solution Overview

We model CSAO as a **session-based learning-to-rank problem** using LambdaRank (LightGBM).

Our system integrates:

- ✅ Sequential cart-aware ranking  
- ✅ Context-rich feature engineering  
- ✅ Semantic menu understanding (AI Edge)  
- ✅ Health-adaptive & price-sensitive re-ranking  
- ✅ Multi-layer cold start fallback  
- ✅ Production-grade latency design (<200ms)  

---

## 🧠 Model Architecture

### 🔹 Core Ranking Engine
- LightGBM with LambdaRank objective  
- Optimized for NDCG@5 and NDCG@10  
- Real-time inference (<10ms)  

### 🔹 Sequential Logic
Cart progression modeled as:

Each cart stage forms a ranking group, enabling contextual transition learning.

---

## 🔥 AI Edge: Semantic Embedding Layer

We incorporated unstructured menu descriptions using TF-IDF embeddings.

Cosine similarity between cart anchor item and candidate add-ons was added as a **semantic_similarity** feature.

### 📈 Impact:
Acceptance improved from **18.21% → 18.37%**

This demonstrates the value of semantic understanding in contextual recommendation.

> In production, this semantic layer can be upgraded to transformer-based embeddings (e.g., Sentence-BERT) for richer personalization.

---

## ❄️ Cold Start Strategy

We implemented conditional fallback logic:

### 👤 New User Strategy

### 🏪 New Restaurant Strategy

### 📊 Cold Start Results

Under simulated **5% new-user and 3% new-restaurant traffic**:

Acceptance decreases from **18.37% → 17.73%**

This demonstrates **graceful degradation** while ensuring relevant recommendations via popularity, semantic similarity, cuisine affinity, and cart-completion heuristics.

---

## 📊 Offline Evaluation

| Metric | Value |
|--------|-------|
| NDCG@5 | 0.539 |
| NDCG@10 | 0.643 |
| Add-on Acceptance Rate | 18.37% |
| Cold Start Acceptance | 17.73% |
| Projected Incremental AOV | ~₹135 per order |

---

## ⚡ Production Readiness

### 🕒 Latency Budget (<300ms)

| Component | Estimated Time |
|------------|---------------|
| Feature Retrieval | 30 ms |
| Candidate Generation | 20 ms |
| Model Inference | 5–10 ms |
| AI Edge Adjustments | 5 ms |
| Network Overhead | 50–80 ms |

**Total Estimated Latency:** ~120–160 ms  

Designed for peak lunch/dinner scalability.

---

## 🧪 A/B Testing Framework

### Control:
Popularity-based baseline  

### Treatment:
Full hybrid CSAO system  

### Primary Metric:
Add-on Acceptance Rate  

### Guardrails:
- Cart-to-Order ratio  
- Cart abandonment  
- Latency (p95 < 250ms)  

Deployment proceeds only if lift is statistically significant and guardrails remain stable.

---

## 📂 Repository Contents

- `CSAO_model.ipynb` → Full pipeline with outputs  
- Evaluation charts (PNG files)  
- Synthetic data generation  
- Model training and evaluation  

---

## 🔗 Submission Links

Colab Notebook: *(Add public link here)*  
Dataset & Code: This repository  

---

## 🏆 Conclusion

Our hybrid structured + semantic CSAO system balances:

- Personalization  
- Cold-start robustness  
- Business alignment  
- Production feasibility  

It is designed not just to maximize accuracy — but to operate reliably at scale.

---
