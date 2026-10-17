# Lab evidence: both mandatory labs completed on IBM LinuxONE

Team ZeroTrace (Mohammed Shehadeh · M.Ghaith Ali · Mohamad Alhomsi) · IBM Z Datathon 2026 · Event code SSF2026

Both prerequisite labs were run end to end on our LinuxONE Community Cloud instance (IBM z17, s390x) before building ZeroTrace.

## Lab 1: Predictive AI hybrid (multi-model): `Churn_Scikit_PyTorch.ipynb`

Client retention analysis on 6,001 customers and 20,000 transactions, joined in pandas, explored, and modelled with a random forest to predict churn.

| Screenshot | What it shows |
|---|---|
| ![](lab1_churn_00_title.png) | Notebook running on LinuxONE (tab name visible) |
| ![](lab1_churn_01.png) | Age vs annual income distribution |
| ![](lab1_churn_02.png) | Feature correlation matrix |
| ![](lab1_churn_03.png) | Churn by age |
| ![](lab1_churn_04.png) | Churn by activity level (box plot) |
| ![](lab1_churn_05.png) | Churn by activity level (beeswarm) |
| ![](lab1_churn_06.png) | Trained RandomForestClassifier |
| ![](lab1_churn_07.png) | Predicted loss by age band |
| ![](lab1_churn_08.png) | Predicted churn probability vs activity level |

## Lab 2: Predictive AI + generative AI: `Loan_Approval_Demo.ipynb`

Loan decisioning combining an XGBoost risk model with IBM Granite (llama.cpp built with IBM zDNN / NNPA acceleration) for document feature extraction, retrieval-augmented recommendation and question answering.

| Screenshot | What it shows |
|---|---|
| ![](lab2_loan_01_load_granite.png) | Loading the IBM Granite model |
| ![](lab2_loan_02_zdnn_check.png) | zDNN shared library present, Granite GGUF valid, build flags `-DGGML_ZDNN=ON` |
| ![](lab2_loan_03_feature_extraction.png) | Granite extracts financial features from bank statements, pay stubs and W-2 |
| ![](lab2_loan_04_xgboost_risk.png) | XGBoost prediction: Low Risk (0.997) |
| ![](lab2_loan_05_recommendation.png) | Granite recommendation: Approve, with reason |
| ![](lab2_loan_06_answer.png) | Granite answers "Why was this applicant considered low risk?" |

## How the labs shaped ZeroTrace

- **Lab 1** (tree-ensemble prediction) → ZeroTrace's ten random-forest slices and ensemble vote.
- **Lab 2** (predictive + generative with Granite) → ZeroTrace's Granite explainer, using the same model and zDNN-accelerated loader, with an added fact-check guardrail.
