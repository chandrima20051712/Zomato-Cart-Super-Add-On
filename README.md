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
