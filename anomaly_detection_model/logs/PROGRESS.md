# Progress Log

## 2026-02-24 — Task: AML Anomaly Detection Literature Review

**What was done:**
- Conducted comprehensive web research across 16+ search queries covering:
  - Graph Neural Networks (GCN, GAT, GraphSAGE, temporal, heterogeneous)
  - Deep learning (LSTM, Transformer, Autoencoder, VAE, GAN)
  - Traditional ML (XGBoost, LightGBM, CatBoost, Isolation Forest, LOF, OCSVM)
  - Contextual/KYC-enhanced detection
  - Feature engineering taxonomy
  - Datasets and benchmarks (Elliptic, AMLSim, PaySim, etc.)
  - Emerging: Federated learning, Explainability (SHAP), Agentic AI, LLMs
  - Class imbalance, concept drift, adversarial robustness
  - Subgraph/community detection for laundering patterns
- Compiled findings into comprehensive LaTeX document (18 pages)
- Generated versioned PDF

**Files created:**
- `paper/aml_anomaly_detection_literature_review.tex` — LaTeX source
- `paper/AML_Anomaly_Detection_Literature_Review_v1.0_20260224.pdf` — Compiled PDF
- `plans/20260224_Literature_Survey_Traditional_ML_AML.md` — Traditional ML sub-survey (from background agent)

**Key findings summary:**
1. XGBoost/LightGBM dominate tabular AML (AUC 0.95-0.99)
2. GNNs add value when graph structure available (F1 improvement ~5-10%)
3. Hybrid rule+ML is the industry standard architecture
4. Self-supervised/contrastive learning addresses label scarcity
5. Transformers/LLMs are the newest frontier (FLAG, TREASURE, 2025-2026)
6. Federated learning enables cross-institution collaboration (+30% accuracy)
7. SHAP explainability is non-negotiable for production deployment
8. Only 18% of institutions have AI/ML fully in production for AML

**Next task planned:** TBD — awaiting human review and direction

---

## 2026-02-24 — Task: v1.1 — Contextual AD Expansion + Entity Resolution

**What was done:**
- Expanded contextual anomaly detection section from ~15 lines to ~3 pages (Song → ROCOD → QCAD → ConQuest → CWAE lineage; King et al. 2025 comparison)
- Added Section 5: Large-Scale Entity Resolution (blocking, matching, tools, AML-specific challenges at 100M+ scale)
- Compiled v1.1 PDF (17 pages)

**Files updated:**
- `paper/aml_anomaly_detection_literature_review.tex`
- `paper/AML_Anomaly_Detection_Literature_Review_v1.1_20260224.pdf`

---

## 2026-02-24 — Task: v1.2 — Supervised Learning, Recommendation Architecture, Multicollinearity

**What was done:**
- Added Section: Supervised Learning with STR-Labeled Data (training data construction, model performance, semi-supervised extensions, PU learning)
- Added Section: Complex Behavior Detection (typologies: structuring, layering, mule networks, TBML; detection approaches; multi-typology supervised models)
- Added Section: Recommended Architecture — Efficacy-Focused AML Detection (5-stage pipeline: feature engineering → unsupervised scoring → supervised detection → graph-based complex behavior → explainability)
- Added FINTRAC regulatory alignment subsection (efficacy mandate, enforcement escalation, OSFI E-23)
- Added implementation roadmap (5 phases)
- Added subsection: Handling Multicollinearity in Feature-Rich AML Pipelines (detection: correlation/VIF/eigenvalue; mitigation: VARCLUS, PCA, mRMR, LASSO, RFE, SHAP-based selection; practical AML-specific guidance)
- Replaced old summary with comprehensive Literature Takeaways
- Compiled v1.2 PDF (22 pages)

**Files updated:**
- `paper/aml_anomaly_detection_literature_review.tex`
- `paper/AML_Anomaly_Detection_Literature_Review_v1.2_20260224.pdf`

**Next task planned:** TBD — awaiting human review and direction
