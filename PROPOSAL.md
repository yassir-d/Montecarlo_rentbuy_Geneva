**Title** : Rent vs Buy Decision Simulator — Geneva
**Category** : Data Science + Machine Learning + Monte Carlo Simulation

1. ## Problem Motivation

Deciding whether to rent or buy a home is one of the most important personal financial decisions. In Geneva, the problem is particularly challenging because:

housing prices are among the highest in Europe,

vacancy rates are extremely low,

mortgage rates fluctuate significantly.

Most online calculators oversimplify the problem: they assume fixed appreciation rates and no uncertainty. This leads individuals to make decisions based on intuition rather than data.

Goal: Build a simulation-based decision tool that compares renting vs buying under uncertainty, using real data and machine learning.
Final output example:

“Based on market conditions in Geneva, buying becomes financially more advantageous than renting after X years with Y% confidence.”

2. ## Data & Legality

Data will be collected exclusively from legal and open data sources:

Data Type	Source	Access
Real estate price index	Swiss Federal Statistical Office (BFS)	Open dataset / CSV
Mortgage interest rates	Swiss National Bank API (SNB)	Public API
Rental price levels & inflation	Open Data Genève / BFS	Open dataset
Optional listing sample (if permitted)	Comparis / ImmoScout24	Only manually downloaded public datasets — no scraping without explicit authorization

No scraping of commercial websites will be performed unless Terms of Service explicitly allow it.

3. ## Methodology (Core Data Science + ML Content)
Step 1 — Data Collection & Preprocessing

Load data from BFS, SNB, Genève Open Data.

Clean, merge, transform into time series (monthly or quarterly).

## Step 2 - Machine Learning Models
Goal	Model	Output
Estimate future real-estate price appreciation	Random Forest Regression + Linear Regression	Forecast % price change
Predict whether buying is financially better than renting	Logistic Regression / Decision Tree	Classification: Buy vs Rent

Evaluation:

Train/test split

RMSE (for regression)

Accuracy + confusion matrix + ROC (for classification)

Optional stretch goal:

K-means clustering to segment Geneva neighborhoods by affordability

## Step 3 — Monte Carlo Simulation

Simulate thousands of future scenarios using stochastic processes:

Housing price growth → lognormal process

Rent inflation → random walk

Interest rates → volatility from SNB data

For each simulation:

Compute net wealth after N years if renting (investing savings)

Compute net wealth after N years if buying (equity + resale value)

Output:

“Buying is financially better in 68.4% of simulated scenarios.”

Step 4 — Visualization

Time evolution of wealth under rent vs buy

Density distribution of outcomes

Probability that buying beats renting

## 4. Success Criteria

The project is successful if:

A working Python tool runs simulations and ML predictions.

Results are data-driven, quantified, and visualized.

Code is version-controlled, structured, and documented.

## 5. Stretch Goals (if time permits)

Streamlit web app for interactive decision tools

Neighborhood affordability ranking using clustering

Export financial reports to PDF