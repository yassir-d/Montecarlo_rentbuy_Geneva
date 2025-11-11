## Rent vs Buy Decision Simulator — Geneva

Monte Carlo Simulation • Data Science • Financial Modeling

Overview

Deciding whether to rent or buy property is one of the most important financial decisions — and in Geneva, it's even more complex due to:

High real-estate prices

Volatile mortgage interest rates

Low rental vacancy rates

Uncertainty in market trends

This project builds a data-driven simulation tool that compares the long-term financial outcome of renting vs buying.
Unlike static online calculators, this tool incorporates uncertainty and randomness.

## What This Project Does

The model simulates thousands of financial scenarios and outputs the probability that buying is better than renting.

Uses:

Component	Description
Monte Carlo simulation	Models uncertainty: price growth, rent inflation, interest rates
Real datasets	Swiss Federal Statistical Office (BFS), SNB API for mortgage rates
(Optional) Machine Learning	Regression to forecast price appreciation
Visualization	Probability distribution of financial outcomes

## Example Output:

"Based on current data, buying becomes more financially advantageous after 7.3 years, with 74% probability."

## Data Science Tools & Methods

Python (NumPy, Pandas, Matplotlib)

Monte Carlo Simulation (lognormal growth processes)

Financial modeling (equity, amortization, opportunity cost)

(Stretch goal) Machine Learning models:

Linear Regression / Random Forest (forecast price change)

Logistic Regression (predict Buy vs Rent decision)