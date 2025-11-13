## Rent vs Buy Decision Simulator — Geneva

Data Science • Machine Learning • Monte Carlo Simulation

## Overview

This project develops a data-driven decision tool to evaluate whether renting or buying a home in Geneva, Switzerland is financially better under market uncertainty.

Unlike simple calculators, it combines machine learning forecasts and Monte Carlo simulations to model housing prices, rent inflation, and mortgage rates.

Example output:
“Buying becomes more advantageous than renting after 7.2 years with 72 % confidence.”

## Objectives

Forecast future housing price appreciation using open Swiss data

Simulate economic uncertainty with Monte Carlo methods

Compare wealth evolution for rent vs buy decisions

Quantify probability that buying outperforms renting

## Methodology
Data

BFS – Real-estate price index

SNB API – Mortgage interest rates

Open Data Genève – Rent levels & inflation
(No unauthorized scraping of commercial sites)

Machine Learning
Task	Model	Validation
Predict price appreciation	Linear Regression / Random Forest	Rolling time-series CV
Classify Buy vs Rent	Logistic Regression	Train/test split
Simulation

Monte Carlo approach:

Price growth ~ lognormal process (μ = ML mean)

Rent inflation ~ random walk

Interest rate ~ AR(1)

Each run computes net wealth for renting vs buying → probability that buying wins.

## Expected Output

Distribution of rent vs buy outcomes

Probability curve of when buying becomes better

Clear visualizations (Matplotlib)

## Success Criteria

Working ML model for housing price appreciation

Probabilistic simulation results

Transparent, reproducible code and documentation