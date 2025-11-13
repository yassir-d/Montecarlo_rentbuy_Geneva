## Project Proposal

## Title: Rent vs Buy Decision Simulator — Geneva
## Category: Data Science + Machine Learning + Monte Carlo Simulation

**1. Problem Motivation**

Deciding whether to rent or buy a home is one of the most important financial decisions individuals face. In Geneva, this decision is particularly complex due to:

Some of the highest housing prices in Europe

Extremely low vacancy rates

Large fluctuations in mortgage interest rates

Most online “rent vs buy” calculators use fixed growth rates and ignore uncertainty. This project aims to build a data-driven decision simulator that incorporates both economic uncertainty and data-based forecasts of housing prices.

Goal: Build a simulation-based and machine learning–enhanced tool that compares renting vs buying under realistic market volatility.

Final Output Example:

“Based on Geneva market data, buying becomes more advantageous than renting after 7.2 years with 72% confidence.”

**2. Data & Legality**

All data sources are open and legally accessible:

Data Type	Source	Access Type
Real estate price index	Swiss Federal Statistical Office (BFS)	Open dataset / CSV
Mortgage rates	Swiss National Bank (SNB) API	Public API
Rental price index & inflation	Genève Open Data / BFS	Open dataset
Optional listing samples	Comparis / ImmoScout24	Manual download only (no scraping unless explicitly allowed)

No automated scraping of commercial sites will be done unless explicitly permitted by their Terms of Service.

**3. Methodology (Core Data Science + ML)**

**Step 1 — Data Collection & Preprocessing**

Load and merge quarterly time series from BFS, SNB, and Genève Open Data.

Clean missing values, compute derived indicators:

Price growth rate, rent inflation, mortgage rate change

Lagged features (t−1, t−2, etc.) to capture trends

Split into training and testing sets (e.g., 2010–2022 train, 2023–2024 test).

**Step 2 — Machine Learning Estimation**
Objective 1: Forecast Real Estate Price Appreciation

Since individual property transaction data is limited, aggregate-level modeling will be used.

Model	Inputs	Output	Validation
Linear Regression	past 4–8 quarters of price index, rent inflation, mortgage rates	Predicted % price change next year	Time-series cross-validation
Random Forest Regressor	same features + volatility indicators	Predicted % price change next year	RMSE, R²

To validate the model:

Use rolling-origin time series validation (train on t₀–tₙ, test on tₙ₊₁).

Evaluate predictive performance on held-out years.

Compare to a baseline (e.g., simple moving average model).

Objective 2: Predict Rent vs Buy Advantage
Model	Inputs	Output	Evaluation
Logistic Regression	predicted appreciation, mortgage rates, rent yield	1 = Buy better, 0 = Rent better	Accuracy, confusion matrix, ROC-AUC
Decision Tree (optional)	interpretable buy/rent threshold	same	

**Step 3 — Monte Carlo Simulation**

Use stochastic modeling to represent economic uncertainty:

House price growth: lognormal process (μ = ML-predicted mean, σ = historical volatility)

Rent inflation: random walk with drift

Mortgage rates: AR(1) process from SNB data

For each simulation (e.g. 10,000 runs):

Compute net wealth after N years for renting vs buying:

Renting: invest down payment and compute portfolio growth

Buying: mortgage amortization + equity growth + resale value

Return probability that buying outperforms renting.

Output:
“Buying outperforms renting in 68% of simulations.”

**Step 4 — Visualization**

Time evolution of expected wealth for rent vs buy

Distribution of financial outcomes (histogram or KDE)

Probability that buying wins as a function of time horizon

**4. Success Criteria**

The project will be successful if:

The model can predict real-estate price appreciation with reasonable accuracy.

The simulation produces probabilistic outcomes for renting vs buying.

All code is modular, tested, and documented.

Results are visualized clearly for interpretation.

**5. Stretch Goals** (If time allows and optional)

Add a Streamlit web app for interactive simulation

Cluster neighborhoods (using K-means) by affordability and volatility

Export a PDF report summarizing simulated outcomes and ML insights