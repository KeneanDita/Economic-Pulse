# EconomicPulse — GitHub Project Backlog

Ready for implementation

8-week milestone plan

Advanced ML

Project: EconomicPulse — Macroeconomic Intelligence & Forecasting Platform

Duration: 8 weeks\
Estimated effort: 120–200 hours\
Primary focus: Ethiopia, with extensibility to other countries.\
Development approach: Research-driven, modular, testable, reproducible.

The backlog below is structured around GitHub milestones, issues, labels, acceptance criteria, and implementation tasks. It is designed to be transferred into a GitHub repository and GitHub Projects.

## 1. Project milestones

| Milestone                | Timeline | Main outcome               |
| ------------------------ | -------- | -------------------------- |
| M1: Data foundation      | Week 1   | Reliable data ingestion    |
| M2: Data exploration     | Week 2   | Validated features         |
| M3: Classical ML         | Week 3   | Baseline predictive models |
| M4: Forecasting          | Week 4   | Time-series experiments    |
| M5: NLP                  | Week 5   | Economic news intelligence |
| M6: Anomaly detection    | Week 6   | Anomaly detection pipeline |
| M7: Deployment           | Week 7   | Working application        |
| M8: Production readiness | Week 8   | Reproducible final system  |

### GitHub labels

Create these labels before importing the issues:

| Label                | Meaning                            |
| -------------------- | ---------------------------------- |
| `type:feature`       | New functionality                  |
| `type:research`      | Research or experimentation        |
| `type:bug`           | Defect                             |
| `type:documentation` | Documentation                      |
| `type:testing`       | Tests and validation               |
| `area:data`          | Data engineering                   |
| `area:ml`            | Classical ML                       |
| `area:deep-learning` | Neural networks                    |
| `area:nlp`           | NLP                                |
| `area:forecasting`   | Time series                        |
| `area:mlops`         | ML infrastructure                  |
| `area:api`           | Backend                            |
| `area:frontend`      | Dashboard                          |
| `priority:high`      | Critical                           |
| `priority:medium`    | Important                          |
| `priority:low`       | Optional                           |
| `good-first-issue`   | Suitable for simpler contributions |

## 2. GitHub issue backlog

Each issue has an objective, implementation tasks, and measurable acceptance criteria.

# EconomicPulse — Engineering Backlog

## EPIC 1: Project foundation and data ingestion

**Milestone:** M1 — Week 1\
**Priority:** High

### Issue #1 — Initialize the project repository

**Labels:** `type:feature`, `area:mlops`, `priority:high`

**Objective:** Establish a maintainable Python project structure.

**Tasks**

- Initialize Git repository.
- Configure Python environment and dependency management using `pyproject.toml`.
- Create the `src/`, `tests/`, `configs/`, `notebooks/`, and `reports/` directories.
- Configure Ruff for linting and formatting.
- Configure Pytest.
- Create `.gitignore`.
- Add README with project description and setup instructions.
- Add GitHub Actions CI workflow.

**Acceptance criteria**

- A clean environment can install the project.
- Tests execute successfully.
- Linting runs automatically through CI.
- Repository structure is documented.

### Issue #2 — Investigate and document data sources

**Labels:** `type:research`, `area:data`, `priority:high`

**Objective:** Determine whether sufficient historical economic data is available.

**Tasks**

- Investigate World Bank APIs.
- Investigate FRED data availability.
- Investigate National Bank of Ethiopia statistics.
- Investigate GDELT news availability.
- Identify candidate target variables.
- Record historical coverage and frequency.
- Identify missing periods.
- Document publication dates and data revisions where available.

**Acceptance criteria**

- At least three usable data sources are documented.
- Each variable has a documented source, unit, frequency, and coverage period.
- Data limitations are recorded.
- One primary forecasting target is selected.

### Issue #3 — Implement automated data ingestion

**Labels:** `type:feature`, `area:data`, `priority:high`

**Objective:** Build reusable ingestion modules.

**Tasks**

- Implement World Bank API client.
- Implement FRED API client where applicable.
- Implement local economic data ingestion.
- Implement news metadata ingestion.
- Add API error handling and retries.
- Add request logging.
- Support incremental updates.
- Save raw responses without overwriting historical snapshots.

**Acceptance criteria**

- Data can be retrieved through reusable functions.
- API failures do not silently corrupt datasets.
- Raw data is preserved.
- Ingestion can be repeated without creating duplicate records.

### Issue #4 — Implement data storage

**Labels:** `type:feature`, `area:data`, `priority:high`

**Objective:** Establish persistent data storage.

**Tasks**

- Configure PostgreSQL.
- Design tables for countries, indicators, observations, sources, and news articles.
- Define primary and foreign keys.
- Add database migrations.
- Implement SQLAlchemy models.
- Implement repository functions.
- Configure database connection through environment variables.

**Acceptance criteria**

- Data can be stored and retrieved.
- Relationships and constraints are enforced.
- Database configuration is reproducible.
- Credentials are not committed to Git.

---

## EPIC 2: Data quality, EDA and feature engineering

**Milestone:** M2 — Week 2\
**Priority:** High

### Issue #5 — Implement data quality validation

**Labels:** `type:feature`, `area:data`, `type:testing`

**Tasks**

- Detect missing values.
- Detect duplicate observations.
- Validate date formats.
- Validate indicator units.
- Detect impossible or suspicious values.
- Check expected observation frequencies.
- Generate data quality reports.

**Acceptance criteria**

- Invalid observations are identified.
- Missing values are quantified.
- Validation results are reproducible.
- Suspicious observations are flagged rather than automatically deleted.

### Issue #6 — Conduct exploratory data analysis

**Labels:** `type:research`, `area:data`

**Tasks**

- Analyze individual economic indicators.
- Examine distributions.
- Investigate correlations.
- Analyze trends and seasonality.
- Examine lagged relationships.
- Investigate structural breaks.
- Perform stationarity tests where appropriate.
- Document major findings.

**Acceptance criteria**

- Every selected feature has an exploratory analysis.
- Major temporal patterns are documented.
- Statistical assumptions are examined.
- Visualizations are reproducible.

### Issue #7 — Build feature engineering pipeline

**Labels:** `type:feature`, `area:data`, `area:forecasting`

**Tasks**

- Implement lag features.
- Implement rolling means.
- Implement rolling standard deviations.
- Create percentage-change features.
- Implement date-based features where appropriate.
- Implement frequency alignment.
- Prevent future information from entering historical features.
- Implement reproducible transformations.

**Acceptance criteria**

- Features are generated consistently.
- Historical features use only information available at prediction time.
- Feature generation supports training and inference.
- Transformations are covered by tests.

---

## EPIC 3: Classical machine learning

**Milestone:** M3 — Week 3\
**Priority:** High

### Issue #8 — Establish forecasting baselines

**Labels:** `type:research`, `area:ml`, `area:forecasting`

**Tasks**

- Implement historical mean baseline.
- Implement naive forecasting.
- Implement seasonal naive forecasting where appropriate.
- Establish chronological training and validation splits.
- Implement evaluation metrics.
- Save baseline results.

**Acceptance criteria**

- Baselines can be reproduced.
- MAE, RMSE, and MASE are calculated where appropriate.
- Evaluation does not use future observations.
- Results are stored for comparison.

### Issue #9 — Train classical regression models

**Labels:** `type:feature`, `area:ml`

**Tasks**

- Implement Linear Regression.
- Implement Ridge Regression.
- Implement Lasso Regression.
- Implement Random Forest.
- Implement XGBoost.
- Implement SVR.
- Compare feature sets.
- Tune selected hyperparameters.

**Acceptance criteria**

- All models use consistent evaluation splits.
- Hyperparameters are tracked.
- Model performance is compared against baselines.
- The best-performing model is selected based on validation results.

### Issue #10 — Implement model explainability

**Labels:** `type:feature`, `area:ml`

**Tasks**

- Calculate feature importance.
- Implement SHAP explanations.
- Generate global explanations.
- Generate individual prediction explanations.
- Compare feature importance across models.

**Acceptance criteria**

- Predictions can be explained.
- Explanations are saved as visualizations.
- Model limitations are documented.

---

## EPIC 4: Advanced time-series forecasting

**Milestone:** M4 — Week 4\
**Priority:** High

### Issue #11 — Implement statistical forecasting models

**Labels:** `type:research`, `area:forecasting`

**Tasks**

- Implement ARIMA.
- Implement SARIMAX where justified.
- Implement Exponential Smoothing.
- Examine residuals.
- Investigate autocorrelation.
- Evaluate prediction intervals.
- Compare against naive baselines.

**Acceptance criteria**

- Statistical models are evaluated using chronological validation.
- Residual diagnostics are documented.
- Forecast horizons are consistent across comparisons.

### Issue #12 — Implement deep learning forecasting

**Labels:** `type:research`, `area:deep-learning`, `area:forecasting`

**Tasks**

- Implement a PyTorch Dataset.
- Implement sliding-window sequence generation.
- Build an LSTM model.
- Experiment with multivariate inputs.
- Implement early stopping.
- Track training and validation loss.
- Experiment with attention or Temporal Fusion Transformer if data permits.

**Acceptance criteria**

- Training is reproducible.
- Sequence generation prevents temporal leakage.
- Training and validation metrics are logged.
- Neural models are compared against statistical baselines.
- Model complexity is justified by performance.

### Issue #13 — Build rolling-origin evaluation

**Labels:** `type:feature`, `area:forecasting`, `type:testing`

**Tasks**

- Implement expanding-window validation.
- Implement rolling-window validation.
- Evaluate one-month forecasts.
- Evaluate three-month forecasts.
- Evaluate six-month forecasts.
- Compare performance across forecasting horizons.

**Acceptance criteria**

- Evaluation can be repeated automatically.
- Results include all selected forecasting horizons.
- No random shuffling is used for temporal validation.
- Results are available in a comparison report.

---

## EPIC 5: NLP and economic news intelligence

**Milestone:** M5 — Week 5\
**Priority:** Medium

### Issue #14 — Build news preprocessing pipeline

**Labels:** `type:feature`, `area:nlp`

**Tasks**

- Ingest news headlines and metadata.
- Remove duplicate articles.
- Normalize text.
- Detect language.
- Filter irrelevant articles.
- Associate articles with timestamps and available economic topics.
- Store processed articles.

**Acceptance criteria**

- News articles are deduplicated.
- Article timestamps are preserved.
- Processing is reproducible.
- Language and coverage limitations are documented.

### Issue #15 — Build sentiment classification models

**Labels:** `type:research`, `area:nlp`, `area:deep-learning`

**Tasks**

- Establish a labeled sentiment dataset.
- Implement TF-IDF features.
- Train Logistic Regression baseline.
- Experiment with pretrained Transformer models.
- Evaluate precision, recall, and F1.
- Investigate class imbalance.
- Document domain-specific limitations.

**Acceptance criteria**

- Sentiment predictions are generated for unseen examples.
- Classification metrics are reported.
- Baseline and Transformer performance are compared.
- Model limitations are documented.

### Issue #16 — Generate economic sentiment indicators

**Labels:** `type:feature`, `area:nlp`, `area:forecasting`

**Tasks**

- Aggregate article sentiment by time period.
- Calculate sentiment distributions.
- Experiment with article volume as a feature.
- Align sentiment features with economic observations.
- Respect actual article publication timestamps.
- Compare forecasting with and without sentiment.

**Acceptance criteria**

- Sentiment indicators are reproducible.
- No future articles enter historical predictions.
- The incremental value of sentiment is measured.

---

## EPIC 6: Anomaly detection

**Milestone:** M6 — Week 6\
**Priority:** Medium

### Issue #17 — Implement anomaly detection models

**Labels:** `type:research`, `area:ml`

**Tasks**

- Implement statistical anomaly detection.
- Implement Isolation Forest.
- Experiment with Local Outlier Factor.
- Experiment with DBSCAN.
- Investigate residual-based anomaly detection.
- Compare detected anomalies.

**Acceptance criteria**

- Multiple approaches are evaluated.
- Anomalies are timestamped.
- Detection thresholds are documented.
- False positives and limitations are investigated.

### Issue #18 — Build anomaly investigation module

**Labels:** `type:feature`, `area:ml`

**Tasks**

- Create anomaly reports.
- Display historical context.
- Associate anomalies with available economic events.
- Generate explanatory visualizations.
- Document investigation results.

**Acceptance criteria**

- Users can inspect detected anomalies.
- Each anomaly includes its relevant indicator and timestamp.
- The system distinguishes unusual observations from confirmed economic events.

---

## EPIC 7: Application development and deployment

**Milestone:** M7 — Week 7\
**Priority:** High

### Issue #19 — Build FastAPI prediction service

**Labels:** `type:feature`, `area:api`, `area:mlops`

**Tasks**

- Initialize FastAPI application.
- Implement health endpoint.
- Implement indicator retrieval endpoint.
- Implement forecasting endpoint.
- Implement anomaly retrieval endpoint.
- Add input validation using Pydantic.
- Add structured logging.
- Document API schemas.

**Acceptance criteria**

- API endpoints return valid responses.
- Invalid inputs are rejected.
- Errors are handled consistently.
- OpenAPI documentation is available.

### Issue #20 — Build Streamlit dashboard

**Labels:** `type:feature`, `area:frontend`

**Tasks**

- Create dashboard layout.
- Display economic indicators.
- Visualize historical trends.
- Display forecasts and prediction intervals.
- Display anomalies.
- Display news sentiment.
- Display model evaluation information.
- Connect dashboard to FastAPI.

**Acceptance criteria**

- Dashboard displays actual data from the backend.
- Users can select indicators and forecasting horizons.
- Forecasts and historical values are clearly distinguished.
- API failures produce understandable error messages.

### Issue #21 — Containerize the application

**Labels:** `type:feature`, `area:mlops`

**Tasks**

- Create backend Dockerfile.
- Create dashboard Dockerfile.
- Configure PostgreSQL service.
- Configure Docker Compose.
- Configure environment variables.
- Add health checks.
- Document startup and shutdown commands.

**Acceptance criteria**

- The application starts through Docker Compose.
- Services communicate correctly.
- Configuration is externalized.
- No credentials are embedded in images.

---

## EPIC 8: Production readiness and research documentation

**Milestone:** M8 — Week 8\
**Priority:** High

### Issue #22 — Implement MLflow experiment tracking

**Labels:** `type:feature`, `area:mlops`

**Tasks**

- Configure MLflow tracking.
- Log model parameters.
- Log evaluation metrics.
- Save model artifacts.
- Track dataset and feature versions.
- Compare experiments.

**Acceptance criteria**

- Experiments can be reproduced.
- Model versions can be identified.
- Results are accessible through the tracking interface.

### Issue #23 — Implement model monitoring

**Labels:** `type:feature`, `area:mlops`

**Tasks**

- Monitor incoming data quality.
- Track prediction errors when actual outcomes become available.
- Implement data drift checks.
- Implement prediction distribution monitoring.
- Generate monitoring reports.
- Define retraining triggers for future use.

**Acceptance criteria**

- Data quality problems are detectable.
- Prediction performance can be monitored.
- Drift alerts are documented.
- Retraining is not triggered blindly by a single statistical signal.

### Issue #24 — Complete automated testing

**Labels:** `type:testing`, `area:mlops`

**Tasks**

- Test ingestion modules.
- Test preprocessing.
- Test feature generation.
- Test model inference.
- Test API endpoints.
- Test database interactions.
- Add integration tests.
- Run tests in GitHub Actions.

**Acceptance criteria**

- Core components have automated tests.
- Critical data leakage scenarios are tested.
- API integration tests pass.
- CI runs successfully.

### Issue #25 — Publish final research and engineering documentation

**Labels:** `type:documentation`, `area:mlops`

**Tasks**

- Write project introduction.
- Document data sources.
- Document methodology.
- Document experimental design.
- Compare model performance.
- Discuss limitations.
- Document deployment architecture.
- Include reproducibility instructions.
- Include dashboard screenshots.

**Acceptance criteria**

- A new developer can reproduce the project.
- Research findings are supported by experiments.
- Limitations are explicit.
- Deployment instructions work from a clean environment.

---

# Project-wide Definition of Done

An issue is complete only when:

- Implementation is committed.
- Code follows project conventions.
- Tests are added where applicable.
- Acceptance criteria are satisfied.
- Documentation is updated.
- No secrets or private data are committed.
- Changes are reviewed and merged into the main branch.

# Weekly Progress Review Template

Complete this every week.

## Week [N] Review

**Milestone:**\
**Planned hours:**\
**Actual hours:**

### 1. Completed work

- \

### 2. Incomplete work

- \

### 3. Technical findings

- \

### 4. Experiments performed

- \

### 5. Results and metrics

- \

### 6. Problems encountered

- \

### 7. Decisions made

- \

### 8. Next week's priorities

- \

### 9. Self-assessment

Rate each from 1–5:

| Category                 | Score |
| ------------------------ | ----- |
| Technical implementation | /5    |
| Research quality         | /5    |
| Code quality             | /5    |
| Testing                  | /5    |
| Documentation            | /5    |

# Initial GitHub Project Setup

Create the following GitHub Project fields:

| Field     | Type              | Values                                               |
| --------- | ----------------- | ---------------------------------------------------- |
| Status    | Single select     | Backlog, Ready, In Progress, Review, Done, Blocked   |
| Priority  | Single select     | High, Medium, Low                                    |
| Milestone | Iteration or text | M1–M8                                                |
| Area      | Single select     | Data, ML, DL, NLP, Forecasting, MLOps, API, Frontend |
| Estimate  | Number            | Estimated hours                                      |

Recommended GitHub Project views:

1. **Roadmap:** Issues grouped by milestone.
2. **Board:** Issues grouped by status.
3. **Priority:** High-priority unfinished issues.
4. **Research:** Issues labeled `type:research`.
5. **Engineering:** Issues labeled `type:feature` or `type:testing`.

# First Sprint: Your Starting Tasks

Do not start training models yet. The first sprint should establish whether the data can support the research questions.

1. Initialize the repository.
2. Investigate World Bank, FRED, and Ethiopian economic data.
3. Select the inflation indicator and forecasting frequency.
4. Build the first ingestion client.
5. Produce a data coverage and quality report.

**First sprint exit condition:** You have a reproducible dataset, a documented data dictionary, and evidence that the primary forecasting target has sufficient historical coverage.

The project should advance based on evidence, not simply because the calendar says the next week has started.

## 3. Recommended GitHub workflow

Use this workflow for every issue:

`Backlog → Ready → In Progress → Review → Done`

Keep only one or two major issues in progress at a time. This will prevent the research, API, NLP, and forecasting components from becoming fragmented.

For your first implementation, prioritize Issues #1–#4. The data feasibility report from Issue #2 should determine whether the original eight-week scope needs adjustment.

## 4. Weekly review

At the end of each week, share your completed issues, GitHub commits, experiments, and blockers. I can assess the implementation against the acceptance criteria and help plan the next sprint.

Suggested review cadence: Every Sunday evening.
