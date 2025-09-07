# Last.FM Music Recommendation  
**Unsupervised Learning Final Project**  

---

## Project Overview  
Music platforms rely heavily on personalization to drive engagement and retention. However, building effective recommender systems under **implicit feedback only** (play counts, no ratings) and **extreme sparsity** (> 99% empty user–item matrix) is a significant challenge.  

This project applies **unsupervised learning** techniques to the Last.FM 1K dataset in order to answer the following question:  
**Can we uncover patterns and build useful music recommendations when user–item interactions are extremely sparse?**  

---

## Objectives  
1. Explore latent patterns via **clustering** of users and tracks.  
2. Evaluate **baseline recommenders** under implicit feedback (MostPopular, UserCF, ItemCF).  
3. Apply **matrix factorization** (SVD vs. NMF) to extract **interpretable music themes**.  
4. Translate technical findings into **practical business insights** for personalization.  

---

## Dataset  
This project uses the **Last.FM 1K Users Dataset**, which contains listening histories of ~1,000 users.  

- GitHub mirror: [lastfm-dataset-1K](https://github.com/eifuentes/lastfm-dataset-1K)  
- Original source: [ocelma.net/MusicRecommendationDataset/lastfm-1K.html](http://ocelma.net/MusicRecommendationDataset/lastfm-1K.html)  

---

## Methodology  
1. **Data Preparation**  
   - Clean and filter active users & tracks  
   - Handle imbalance and sparsity  
   - One-hot encoding, scaling, and visualization  

2. **Unsupervised Models**  
   - Clustering: TruncatedSVD + KMeans  
   - Recommendation: MostPopular, UserCF, ItemCF  
   - Matrix Factorization: SVD vs. NMF  

3. **Evaluation Metrics**  
   - Clustering → Silhouette Score  
   - Recommendation → Precision@K, Recall@K, Hit Rate  
   - Matrix Factorization → RMSE & interpretability  

4. **Interpretation & Insights**  
   - From metrics to business-level value  
   - Applications in playlist generation, retention, and personalization  

---

## Key Findings  
- **User Clusters**: Weak separation, mostly “heavy vs. light listeners”.  
- **Track Clusters**: More meaningful, moderate Silhouette score (≈0.32), aligned with genres/moods.  
- **Recommendation Baselines**:  
  - MostPopular gave a stable lower bound (≈0.3% hit rate).  
  - UserCF / ItemCF / SVD failed under sparsity.  
- **Matrix Factorization**:  
  - NMF achieved lower RMSE (~7.07 vs. 11.19 for SVD).  
  - NMF factors are interpretable (e.g., “indie rock”, “calm piano”), supporting explainability.  

---

## Conclusion & Next Steps  
**Conclusion**  
- Unsupervised learning produced valuable insights: weak user grouping, but strong track themes.  
- MostPopular baseline is consistent, but personalization under implicit feedback remains challenging.  
- NMF stands out as the best compromise between accuracy and interpretability.  

**Next Steps**  
- **Algorithms**: Explore implicit-feedback-specific methods (ALS, BPR, WARP), hybrid recommenders, and Transformer-based models.  
- **Data**: Enrich with metadata (lyrics, genres, audio embeddings) for multimodal recommendations.  
- **Business**: Build a recall → re-rank → interpretation loop to balance accuracy and user transparency.  

---

## Repository Contents  
- `LastFM_Notebook_ULFinalProject.ipynb` → Full analysis and modeling notebook  
- `LastFM_Slides_ULFinalProject.pdf` → Presentation slides  
- `LastFM_README_ULFinalProject.md` → Extended report-style README
