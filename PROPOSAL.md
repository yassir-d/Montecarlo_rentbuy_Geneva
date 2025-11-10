# Project Proposal  
**Title:** Rent vs Buy Decision Simulator — Geneva  
**Category:** Simulation + Data Science + Machine Learning  

## 1. Problem Motivation

For most working adults, deciding whether to rent or buy a property is the biggest financial decision of their lives. In Geneva, the decision is even more complex due to high prices, low vacancy rates, and large variability in mortgage interest rates. People often rely on intuition or simplistic calculators, which fail to model uncertainty and risk.

**Goal:** Build a decision-support tool that simulates the financial outcomes of renting vs buying over time under uncertainty and market volatility.

Unlike typical calculators, my tool incorporates:
- randomness (Monte Carlo simulation),
- uncertainty on market conditions (interest rates, price appreciation, rent inflation),
- machine learning predictions for real-estate trends (optional stretch goal).

The final output will answer:

> _"In Geneva, based on current conditions, buying becomes financially better than renting after X years with Y% confidence."_


## 2. Planned Approach & Technical Plan

### Core Components
1. **Monte Carlo Simulation**
   - Simulate thousands of future possible scenarios:
     - housing price appreciation (lognormal process)
     - rent inflation (random walk)
     - interest rate fluctuations
   - Compute final net wealth after N years for buying vs renting.

2. **Data Collection & Processing**
   - Collect historical data for Geneva:
     - rent levels → Comparis.ch (web scraping (legal) / imoscout24(limited))
     - real-estate prices → Swiss Federal Statistical Office (API or CSV)
     - mortgage rates → Swiss National Bank API

3. **Machine Learning**
   - Regression model (Random Forest and/or Linear Regression)
   - Predict future rent increases and property price appreciation.

4. **Visualization**
   - Distribution of financial outcomes (histograms, violin plots)
   - Probability of buying being superior (e.g., "Buying wins in 73% of simulations")

5. **Testing**
   - Unit tests validating simulation logic and numerical consistency.

## 3. Expected Challenges

- Real-estate datasets for Geneva are messy or incomplete → must use scraping & cleaning.
- Monte Carlo simulation requires careful parameter calibration (volatility, drift).
- Ensuring the tool is transparent and interpretable for users.

## 4. Success Criteria

The project will be considered successful if:
- A working simulation computes the rent vs buy financial outcome.
- The tool outputs a probability score (e.g., "Buying is better in 68% of cases").
- Visualizations are clear and interpretable.
- The code follows good structure, documentation, testing, and version control.

## 5. Stretch Goals

- Add a simple UI (Streamlit)
- Add ML-based forecasting for rent and price appreciation
- Export final results as downloadable PDF report

---

