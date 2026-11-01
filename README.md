# Economic-Pulse

An intelligent macroeconomic monitoring, forecasting, and anomaly detection platform.

# Tailored ML Capstone: Macroeconomic Intelligence & Forecasting System

Advanced level

8 weeks

120–200 hours

Based on your assessment, I would not recommend spending your time on introductory ML exercises, basic neural networks, or standard Kaggle classification competitions.

You already have experience with the main ML and deep learning frameworks. Your next step should be to strengthen three areas:

1. Research ability: Form hypotheses, design experiments, compare approaches, and defend technical decisions.
2. Advanced ML development: Work with complex datasets, sophisticated models, temporal validation, and model interpretability.
3. ML engineering: Build reproducible pipelines and deploy models that can operate beyond a Jupyter notebook.

I would retain the economic forecasting direction from the earlier proposal, but make it considerably more rigorous.

## 1. Project definition

[Sherlock AI](https://images.openai.com/static-rsc-4/8RNTNxjs1OSihEdVnjKdzIRAlQosYPgt8y57Na4lnVnivUbX_htggPbVH1eHGyiUjGEeX-6qvdau3w04dImAhvCzGGl3Vesp-emvjyyQ8I1wgSQSxESvQj7GdTAPQ7k87QGgboTdU0o42NTxkNLvAKzPlwa_-f_xxoCMUzu0UHI?purpose=inline)

[meetsherlock.ai](https://www.meetsherlock.ai/?utm_source=chatgpt.com)

# EconomicPulse

An intelligent macroeconomic monitoring, forecasting, and anomaly detection platform.

### Problem statement

Build a system that analyzes historical economic indicators, forecasts future economic conditions, detects unusual economic movements, and analyzes economic news to identify potentially relevant events.

Initially, focus on Ethiopia, with the architecture designed to support other countries later.

### Core capabilities

| Module            | Function                                               |
| ----------------- | ------------------------------------------------------ |
| Forecasting       | Predict inflation and selected economic indicators     |
| Classical ML      | Identify important economic predictors                 |
| Deep learning     | Experiment with multivariate forecasting architectures |
| NLP               | Extract sentiment and economic events from news        |
| Anomaly detection | Identify unusual movements in indicators               |
| Explainability    | Explain model predictions using SHAP                   |
| Deployment        | Expose predictions through an API and dashboard        |
| Monitoring        | Track data quality and model performance               |

The interesting part is that these modules must work together rather than exist as unrelated experiments.

### Research questions

Your project should investigate questions such as:

- Do machine learning models outperform statistical forecasting baselines?
- Does adding international commodity prices improve inflation forecasting?
- Does economic news sentiment provide additional predictive information?
- How well do models perform when economic conditions change?
- Can anomaly detection identify meaningful changes in economic indicators?

These questions give the project a research component instead of making it merely an application.

## 2. Dataset strategy

Use multiple sources, but start with a small, well-defined dataset.

[World Bank Open Data | Open data, Data, Sample survey](https://images.openai.com/static-rsc-4/grLQXWB6o1YRcfTOO3JceVJfHB7kcBNzj8M-U3Yuvr8L8WIoYIim1hjFl0oQGpY3h_877R7v2Q3itmI8gEKRRtR037NetLKqj3KMORa_hmhfDepleoIxQxopwkQ45rICxGQimpnNov52DQHcSnGoOA6756eJdF34O_gqDgk_2b8?purpose=inline)

1\. World Bank Open Data

GDP, inflation, unemployment, exchange rates, and other economic indicators.

[Access datasets](https://data.worldbank.org/?utm_source=chatgpt.com)

[FRED Data Dashboard for Educators | Scott Wolla](https://images.openai.com/static-rsc-4/Wy2TVfmBtpzg-4IVd6wCO9m3E0tFjaqimz1uQOpEfleU7joL3m8IePqLtbww9-Mol6ZbjMnW1j_iGx-QB3KZhmiG4TDJ1YxjrjKDpHBBdpeH-Xk5jPcC_5x6YpvbODOwH2QyFIMjisllABv3JI5IB9zYxbtVG0-z-aDOKuqLz0I?purpose=inline)

2\. FRED

Global commodity prices, interest rates, exchange rates, and other economic time series.

[Access datasets](https://fred.stlouisfed.org/?utm_source=chatgpt.com)

[The GDELT Project](https://images.openai.com/static-rsc-4/SbaA3HiJ89QMXMPDlpKCX-yRKRbSr5W7AIZAdUF6JZaUs2dgGEwiNpWPAdx56ExB2KHzpo04L8FfAClj99j1GHGlY7wXVjxB-TeCfDNwdNzHOEE_dWTdOF8lgAxMdYfK3qrXeUFUpEirDpaBQyEGwZ8R2wK588ples5KD2Ne3ns?purpose=inline)

3\. GDELT Project

News articles, event data, and international news coverage.

[Access datasets](https://www.gdeltproject.org/?utm_source=chatgpt.com)

[Penalty for Non compliance with the Directives of the National Bank Directive No.ONPS/08/2022 - DFS Ethiopia Hub](https://images.openai.com/static-rsc-4/A-lpm709j94wfbOaZqtoK4Qm8npMgGYy5mZgSZgvfn_O0E6Zq2EYYWkICHDR7jkhQaMc5GrnrkeWmuh9XoDZg-90q0B4NqNgHsW_c-ZGpU8ZGUH6Eyq-POxTqZU1kDTTQICGXElnJWSzf2PENVs8jN7s_dUarU6paAzG65MA70U?purpose=inline)

4\. National Bank of Ethiopia

Local monetary and financial statistics, exchange rates, and publications.

[Official website](https://nbe.gov.et/?utm_source=chatgpt.com)

### Proposed features

Your primary forecasting dataset could contain:

| Feature        | Description                        |
| -------------- | ---------------------------------- |
| Inflation      | Historical CPI inflation           |
| Exchange rate  | Local currency exchange rate       |
| Oil prices     | International oil prices           |
| Food prices    | Global food price index            |
| Interest rates | Available monetary policy rates    |
| Money supply   | Monetary aggregates                |
| GDP growth     | Economic growth indicators         |
| News sentiment | Aggregated economic news sentiment |

Important data consideration: Ethiopian economic data may have missing periods, changing definitions, different reporting frequencies, and publication delays. These are part of the research problem.

Do not assume all indicators are available monthly. Start by auditing their actual frequency and coverage. Avoid interpolating annual GDP into monthly observations and treating those artificial values as real measurements.

## 3. Technical architecture

I recommend separating the project into independent components with clear interfaces.

[Machine Learning Pipeline: Stages, Benefits & Best Practices](https://images.openai.com/static-rsc-4/-YaNCXAwfZonXvZ3QH_4pQ88nuDq3k_M3KdeBvgektUEFLowdhENVzEUF3J9h1txLuLiGmaMZ4-RvTbK5L3cKKybiPRrtxmmltxNyotfrjJTwG9zV20jr937psGcMUGoKkaEVJi4C6wTFwnQ4Bh373HvkkyZtm72FcmySe_vB84?purpose=inline)

[upgrad.com](https://www.upgrad.com/blog/machine-learning-pipeline/?utm_source=chatgpt.com)

The proposed architecture:

```
       DATA SOURCES
   ┌──────────────────┐
   │ World Bank       │
   │ FRED             │
   │ GDELT            │
   │ National Bank    │
   └────────┬─────────┘
            │
            ▼
   ┌──────────────────┐
   │ Data Ingestion   │
   │ API / ETL        │
   └────────┬─────────┘
            │
            ▼
   ┌──────────────────┐
   │ Data Processing  │
   │ Cleaning / EDA   │
   │ Feature Pipeline │
   └────────┬─────────┘
            │
            ▼
   ┌──────────────────┐
   │ Model Training   │
   │                  │
   │ Classical ML     │
   │ Deep Learning    │
   │ NLP              │
   │ Anomaly Detection│
   └────────┬─────────┘
            │
            ▼
   ┌──────────────────┐
   │ Model Evaluation │
   │ MLflow           │
   └────────┬─────────┘
            │
            ▼
   ┌──────────────────┐
   │ FastAPI           │
   │ Prediction API    │
   └────────┬─────────┘
            │
            ▼
   ┌──────────────────┐
   │ Streamlit         │
   │ Analytics UI      │
   └──────────────────┘
```

### Recommended technology choices

| Component            | Technology                |
| -------------------- | ------------------------- |
| Data processing      | Pandas, Polars, NumPy     |
| Statistical analysis | Statsmodels               |
| Classical ML         | Scikit-learn, XGBoost     |
| Deep learning        | PyTorch                   |
| NLP                  | Hugging Face Transformers |
| Explainability       | SHAP                      |
| Experiment tracking  | MLflow                    |
| Data versioning      | DVC                       |
| Database             | PostgreSQL                |
| API                  | FastAPI                   |
| Dashboard            | Streamlit                 |
| Deployment           | Docker Compose            |
| Testing              | Pytest                    |

I would prioritize PyTorch over TensorFlow for this project. There is no need to use both frameworks in the same training pipeline.

## 4. Eight-week implementation plan

At 15–25 hours per week, you have approximately 120–200 hours. This is enough to build a serious project if the scope is controlled.

Week 1 — Data engineering and collection

15–20 hours

Objective: Build a reliable data collection system.

Tasks:

- Investigate the available economic datasets.
- Identify target variables and their frequencies.
- Retrieve historical data through APIs.
- Build reusable ingestion modules.
- Handle missing observations and inconsistent dates.
- Store raw data separately from processed data.

Deliverables:

- Data ingestion pipeline.
- Dataset documentation.
- Initial PostgreSQL database.
- Data quality report.

Engineering challenge: Different data sources have different update frequencies and publication delays.

Week 2 — EDA and feature engineering

15–20 hours

Objective: Understand the underlying economic data.

Tasks:

- Perform univariate and multivariate analysis.
- Investigate correlations and lagged relationships.
- Analyze seasonality and trends.
- Test stationarity where appropriate.
- Engineer lag features.
- Create rolling averages and volatility features.
- Investigate structural breaks.

Techniques:

- ACF and PACF.
- Augmented Dickey-Fuller tests.
- Correlation analysis.
- Mutual information.
- Statistical visualization.

Deliverables:

- EDA notebook.
- Feature engineering pipeline.
- Data dictionary.
- Initial research hypotheses.

Week 3 — Classical machine learning

15–25 hours

Objective: Establish strong predictive baselines.

Models:

- Linear Regression.
- Ridge and Lasso.
- Random Forest.
- XGBoost.
- Support Vector Regression.

Experiments:

- Compare different feature sets.
- Perform chronological validation.
- Analyze feature importance.
- Experiment with regularization.
- Use SHAP for model explanations.

Deliverables:

- Baseline model comparison.
- Experiment tracking in MLflow.
- Model evaluation report.

Research question: Do nonlinear models offer a meaningful improvement over simpler statistical and linear models?

Week 4 — Advanced time-series forecasting

20–25 hours

Objective: Build forecasting models that account for temporal dependencies.

Models:

- Naive and seasonal naive baselines.
- ARIMA / SARIMAX.
- Exponential Smoothing.
- Gradient boosting with lag features.
- LSTM.
- Temporal Fusion Transformer (optional advanced experiment).

Experiments:

- Univariate versus multivariate forecasting.
- Different forecasting horizons.
- Rolling-origin evaluation.
- Recursive versus direct forecasting.
- Prediction intervals.

Deliverables:

- Forecasting pipeline.
- Model comparison.
- Forecast visualization.

Important: Do not assume LSTM or Transformers will outperform simpler models. Monthly macroeconomic datasets are often too small for complex neural architectures. Use deep learning only where the data volume and experimental results justify it.

Week 5 — NLP and economic news intelligence

15–25 hours

Objective: Extract useful signals from unstructured economic news.

Tasks:

- Collect economic news headlines and metadata.
- Remove duplicates and irrelevant articles.
- Perform text preprocessing.
- Implement TF-IDF with Logistic Regression.
- Experiment with pretrained Transformer models.
- Aggregate sentiment by day or month.
- Explore relationships between sentiment and economic indicators.

Models:

- TF-IDF.
- Logistic Regression.
- DistilBERT.
- FinBERT as an experimental baseline, recognizing its financial-domain limitations.

Deliverables:

- News processing pipeline.
- Sentiment classification model.
- Sentiment time series.

Research question: Does news sentiment improve forecasting beyond information already contained in historical economic indicators?

Treat sentiment as an experimental feature, not an established economic predictor.

Week 6 — Anomaly detection and explainability

15–20 hours

Objective: Detect unusual economic behavior.

Algorithms:

- Isolation Forest.
- Local Outlier Factor.
- DBSCAN.
- Statistical residual-based anomaly detection.

Tasks:

- Detect unusual changes in economic indicators.
- Identify periods of abnormal volatility.
- Compare statistical and ML-based approaches.
- Investigate historical economic events.
- Explain model predictions using SHAP.

Deliverables:

- Anomaly detection pipeline.
- Anomaly reports.
- Explainability module.

    Week 7 — Model serving and deployment

    15–25 hours

    Objective: Turn the research code into a usable application.

Tasks:

- Build a FastAPI backend.
- Create prediction endpoints.
- Implement model loading and validation.
- Build a Streamlit dashboard.
- Containerize the application.
- Add automated tests.
- Connect the application to PostgreSQL.

Deliverables:

- Working REST API.
- Interactive dashboard.
- Docker Compose configuration.
- API documentation.

    Week 8 — Production readiness and research report

    15–20 hours

    Objective: Make the project reproducible and demonstrate its technical value.

Tasks:

- Implement model versioning.
- Track training experiments.
- Add data validation.
- Monitor prediction errors.
- Investigate model drift.
- Write technical documentation.
- Document limitations and research findings.

Deliverables:

- Complete repository.
- Reproducible training pipeline.
- Model evaluation report.
- Research report.
- Deployed application.

## 5. Model evaluation strategy

This is where I would expect you to demonstrate advanced ML knowledge.

Do not simply report accuracy or R².

### Forecasting metrics

| Metric               | Purpose                                                       |
| -------------------- | ------------------------------------------------------------- |
| MAE                  | Average absolute prediction error                             |
| RMSE                 | Penalizes larger prediction errors                            |
| MASE                 | Compares against a naive forecasting baseline                 |
| sMAPE                | Measures relative forecasting error                           |
| Directional accuracy | Measures whether predicted movement has the correct direction |

Use at least three forecasting horizons, for example:

- One month ahead.
- Three months ahead.
- Six months ahead.

Use rolling-origin evaluation instead of relying on one train/test split.

### Experimental design

Your model comparisons should look something like this:

| Experiment | Features                                  |
| ---------- | ----------------------------------------- |
| E1         | Historical inflation only                 |
| E2         | Inflation + exchange rates                |
| E3         | All available economic indicators         |
| E4         | Economic indicators + news sentiment      |
| E5         | E4 + alternative forecasting architecture |

This gives you a way to measure whether each additional information source actually improves predictive performance.

Also account for publication dates. A historical economic indicator should not be available to a simulated forecast before it was actually published.

## 6. Research component

To make this more than an engineering portfolio project, write a small research report.

Suggested title:

Evaluating Classical Machine Learning, Deep Learning, and News Sentiment for Macroeconomic Forecasting in Ethiopia.

Structure:

1. Introduction and problem definition.
2. Related research.
3. Dataset description.
4. Methodology.
5. Experimental design.
6. Results and comparisons.
7. Limitations.
8. Conclusion.

Useful research topics:

- Forecasting under non-stationary conditions.
- Statistical versus deep learning forecasting.
- The value of external variables.
- News sentiment as an auxiliary predictor.
- Explainable machine learning in economic forecasting.

Do not claim causal relationships from predictive correlations.

## 7. Prerequisites and knowledge to refresh

You do not need to relearn Python or introductory ML. Focus on the concepts that will matter for this project.

| Area                 | Concepts to refresh                                             |
| -------------------- | --------------------------------------------------------------- |
| Statistics           | Hypothesis testing, confidence intervals, distributions         |
| Time series          | Stationarity, autocorrelation, cointegration, structural breaks |
| ML                   | Regularization, ensemble learning, cross-validation             |
| Deep learning        | Sequence modeling, attention, optimization                      |
| NLP                  | Tokenization, embeddings, Transformer architecture              |
| MLOps                | Experiment tracking, model versioning, data validation          |
| Software engineering | Testing, modular architecture, API design                       |

### Recommended learning resources

[Forecasting: Principles and Practice, the Pythonic Way](https://images.openai.com/static-rsc-4/sJa0ip0Qaii8GC4G_dCjwmTAVtvJFN5t8djEGWawRP9CKuEog8umNf8hUu0lpq8I6OtugJS4bIdA4gKRgmMl1Ab_hCcJ2Q41T6WjV6CKZhJpjlFTbDoQJfqSBDtZ7JoArYUXlnlg_EDW86WMENJMCNhSngp3dCnS5Dh0NuHDT3I?purpose=inline)

Forecasting: Principles and Practice

Excellent reference for statistical forecasting, evaluation, and time-series methodology.

[Read online for free](https://otexts.com/fpp3/?utm_source=chatgpt.com)

[Dive into Deep Learning - Zhang, Aston; Lipton, Zachary C.; Li, Mu; Smola, Alexander J.: 9781009389433 - AbeBooks](https://images.openai.com/static-rsc-4/qnGXI3BK8lmqJRAAyXutTPVV39rIP5CalYZDRCni5AfmXbshRfqly-GIdvEY6VBHm_DHL2-eRpca2C1dBKD5GYQ-NSIV5BQ3-ySK8M1PG2HmmzKrmZmTLk4ElKJKzCPjSBcafELLpDUX0X-3e8UlPHABb9EPcg0SkxlvhfWnJO0?purpose=inline)

Dive into Deep Learning

Deep learning theory, implementation, and practical experiments.

[Read online](https://d2l.ai/?utm_source=chatgpt.com)

[Books](https://images.openai.com/static-rsc-4/OdJpR0Grf_y2GYTci1qR8D6fCGXP3IKf7SKlen4NviamJJsrJV49RfeSfBi25l5DARlJBrRgSsiDwQcOAoInwSXDc2-pRjp5iKNU6Avksrk9jtaXUugMil23XOlpZvQOgJhsYiBWjbAZ9T9aFtpu60BUGA8MfBHIw8luUKWcu_w?purpose=inline)

Designing Machine Learning Systems

ML system architecture, deployment, data pipelines, and production considerations.

[Book details](https://www.oreilly.com/library/view/designing-machine-learning/9781098107956/?utm_source=chatgpt.com)

[Natural Language Processing with Transformers, Revised Edition - by Lewis Tunstall & Leandro Von Werra & Thomas Wolf (Paperback) : Target](https://images.openai.com/static-rsc-4/2IgROY5Yqb7Qkrrf31XnPnPZV4qh5oay9ng6sTHcwQeWWtRWQUu31cbH7wuOrBWHc8YYuqHgHBablwZng54xogSbpOCQKMWovzPG4geaDFxyGkuOHfwszN1fCM3R_sxfCfLxnI3czWZrtDp1p1hG2h9Qm4AxB4Cc7CIv9b3ZEI4?purpose=inline)

Hugging Face NLP Course

Practical Transformer implementation and fine-tuning.

[Free course](https://huggingface.co/learn/nlp-course/?utm_source=chatgpt.com)

[Made With ML - Goku Mohandas | Podcast #34](https://images.openai.com/static-rsc-4/rG4QB6F59P_LQj8SB6VaP_4nHHdKOnGB26a6_8avD3Oau7rOUHsd8rWwicTMATgzMXiUDe84Y3ytl6NwOQ8Xtjs6s4c67azr88ryRErWf7g1AzDvTlIkWTRpu4uvhmNFIlM0nWlwFj2c8L8LuUtXGqpsBwKYKXPA7d7nbsfdGyY?purpose=inline)

Made With ML

Practical ML engineering, testing, pipelines, and deployment.

[Explore course](https://madewithml.com/?utm_source=chatgpt.com)

## 8. Recommended GitHub repository structure

Organize the project as a proper software engineering repository from the beginning.

```
economic-pulse/
│
├── configs/
│   ├── data.yaml
│   ├── training.yaml
│   └── model.yaml
│
├── data/
│   ├── raw/
│   ├── processed/
│   └── external/
│
├── notebooks/
│   ├── 01_data_exploration.ipynb
│   ├── 02_feature_engineering.ipynb
│   ├── 03_classical_ml.ipynb
│   ├── 04_forecasting.ipynb
│   ├── 05_nlp.ipynb
│   └── 06_anomaly_detection.ipynb
│
├── src/
│   ├── ingestion/
│   ├── preprocessing/
│   ├── features/
│   ├── models/
│   │   ├── classical/
│   │   ├── forecasting/
│   │   ├── deep_learning/
│   │   ├── nlp/
│   │   └── anomaly_detection/
│   ├── evaluation/
│   └── monitoring/
│
├── api/
│   ├── main.py
│   ├── routes/
│   └── schemas/
│
├── dashboard/
│
├── tests/
│
├── reports/
│   ├── figures/
│   └── research_report.md
│
├── docker-compose.yml
├── Dockerfile
├── pyproject.toml
├── dvc.yaml
├── README.md
└── .gitignore
```

Do not put large datasets, credentials, or trained model binaries directly into Git. Use DVC or suitable artifact storage.

## 9. What counts as project completion?

I would use these acceptance criteria:

Project completion checklist

0/12

Automated data ingestion from at least three sources

Documented data quality and preprocessing pipeline

At least three classical/statistical forecasting baselines

At least one deep learning forecasting experiment

NLP pipeline with evaluated sentiment classification

Anomaly detection with documented validation

Leakage-safe chronological evaluation

Experiment tracking with MLflow

Prediction API with automated tests

Dockerized dashboard and API

Model monitoring and reproducibility documentation

Research report with experimental conclusions

## 10. Scope management: what I would prioritize

There is a risk of making this project too broad.

I recommend the following priorities:

Must have

- Inflation forecasting.
- Classical ML and statistical baselines.
- Proper time-series evaluation.
- FastAPI deployment.
- Experiment tracking.

Should have

- Deep learning comparison.
- News sentiment analysis.
- Anomaly detection.
- SHAP explanations.

Stretch goals

- Temporal Fusion Transformer.
- Multicountry forecasting.
- Automated retraining.
- Advanced model drift monitoring.

If the Ethiopian monthly dataset is too limited for neural forecasting, retain the economic focus but use a larger, established time-series dataset for the deep learning experiments. Do not manufacture data to justify a model.

## My recommendation for how to approach this

Treat the project as three interconnected deliverables:

1. Research: Discover which models and information sources actually improve forecasting.
2. Engineering: Build a reproducible pipeline that someone else can run.
3. Product: Deliver a working application that makes the research results accessible.

The strongest portfolio outcome is not a dashboard with impressive charts. It is a system whose predictions have been rigorously evaluated, whose limitations are documented, and whose entire workflow can be reproduced.

Your next milestone should be Week 1: data discovery and feasibility assessment. Before writing model code, establish whether you have sufficient historical coverage, consistent frequencies, and trustworthy publication dates for your target variables.

I can turn this roadmap into a GitHub-ready project backlog with individual issues, acceptance criteria, implementation tasks, and weekly progress reviews.
