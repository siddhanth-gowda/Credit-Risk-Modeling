# Credit Risk Modeling and Portfolio Stress Testing

## Overview

This project implements a comprehensive **Credit Risk Analytics and Stress Testing Framework** in Python to evaluate the evolution, stability, and risk exposure of a credit portfolio over a multi-year horizon.

The system models **rating migration dynamics, probability of default (PD), expected loss (EL), and stress scenarios** using transition matrices and credit risk theory.

The objective is to enable **quantitative risk measurement, capital planning, and portfolio stress testing** aligned with real-world banking risk management practices.

---

## Key Features

- Rating transition matrix construction
- Probability of Default (PD) estimation
- Expected Loss (EL) modeling using PD, LGD, and EAD
- Credit migration analysis
- Portfolio concentration measurement (HHI)
- Rating Drift Index (RDI) analysis
- Cumulative Probability of Default (CPD)
- LGD stress testing scenarios
- Migration stress testing scenarios
- Portfolio stability and downgrade risk analysis

---

## Dataset

The dataset contains:

- Multi-year credit rating data
- Borrower migration between rating classes
- Exposure at Default (EAD)
- Loss Given Default (LGD)
- Rating categories: AAA, AA, A, BBB, BB, B, C, D

The dataset tracks portfolio evolution over a **10-year horizon**.

---

## Methodology

---

### 1. Exploratory Data Analysis

Initial analysis focuses on understanding portfolio composition and credit quality dynamics.

#### Rating Composition Analysis

- Rating distribution analyzed across all years
- Investment grade and speculative grade proportions evaluated
- Portfolio stability assessed

Key finding:

- Stable rating distribution across all classes indicates consistent underwriting discipline.

---

#### Rating Drift Index (RDI)

Measures average rating movement over time.

Formula:

\[
RDI = Average(\text{Rating movement})
\]

Interpretation:

- Positive RDI → overall upgrades
- Negative RDI → overall downgrades

This helps identify stress periods and credit deterioration cycles.

---

#### Portfolio Concentration (HHI)

Herfindahl-Hirschman Index used to measure concentration risk:

\[
HHI = \sum p_i^2
\]

Where:

- \(p_i\) = proportion of exposures in rating category i

Low HHI indicates strong diversification.

---

### 2. Transition Matrix Construction

Transition matrices capture migration probabilities between rating categories.

Structure:

\[
P_{ij} = \Pr(\text{Rating at time t+1 = j | Rating at time t = i})
\]

These matrices are used to model:

- Rating migration behavior
- Default probabilities
- Credit deterioration patterns

---

### 3. Probability of Default (PD) Modeling

Rating-level PDs are derived from transition matrices.

Portfolio PD calculated as:

\[
PD_{portfolio} =
\sum (Exposure_i \times PD_i)
\]

PD analysis reveals:

- Cyclical credit risk patterns
- Periods of elevated default risk
- Mean-reverting credit conditions

---

### 4. Expected Loss (EL) Modeling

Expected Loss calculated using the standard credit risk formula:

\[
EL = PD \times LGD \times EAD
\]

Where:

- PD = Probability of Default
- LGD = Loss Given Default
- EAD = Exposure at Default

Expected Loss is computed:

- Per rating category
- Per year
- At portfolio level

This enables dynamic loss forecasting.

---

### 5. Cumulative Probability of Default (CPD)

Measures default risk accumulation over time.

\[
CPD = 1 - \prod (1 - PD_t)
\]

This quantifies long-term credit risk exposure.

Example findings:

- CPD increases significantly over long horizons
- Indicates persistent residual portfolio risk

---

### 6. Stress Testing Framework

The project implements two major stress scenarios:

---

#### Scenario 1: LGD Stress Testing

LGD values increased to simulate economic downturn.

Effect:

- Expected Loss increases significantly
- Demonstrates sensitivity to recovery rate assumptions

---

#### Scenario 2: Rating Migration Stress Testing

Transition matrix adjusted to simulate credit deterioration.

Impact:

- Increased downgrade probabilities
- Significant rise in Expected Loss
- Quantifies systemic credit risk vulnerability

---

### 7. Portfolio Stability and Risk Metrics

Additional metrics computed include:

---

#### Rating Stability Analysis

Measures probability of rating remaining unchanged.

Helps identify:

- Stable credit categories
- Volatile rating segments

---

#### Net Downgrade Ratio (NDR)

Measures downgrade intensity:

\[
NDR =
\frac{\text{Downgrades} - \text{Upgrades}}{\text{Total migrations}}
\]

Identifies stress periods.

---

## Results Summary

Key insights obtained:

- Portfolio exhibits stable long-term credit composition
- Default risk shows cyclical patterns
- Expected Loss remains bounded under normal conditions
- Stress testing reveals significant risk under adverse scenarios
- Portfolio is highly sensitive to LGD and rating deterioration
- Long-term cumulative default risk is substantial

---

## Applications

This framework can be used for:

- Bank credit risk modeling
- Basel regulatory capital calculations
- Stress testing under Basel III / IFRS 9
- Risk management in lending institutions
- Portfolio risk monitoring
- Credit portfolio optimization

---

## Tech Stack

- Python
- NumPy
- Pandas
- Matplotlib
- Seaborn
- SciPy

---

## Future Improvements

Possible extensions include:

- Monte Carlo credit risk simulation
- Correlated default modeling
- Copula-based credit risk
- Macro-economic factor modeling
- Machine learning credit scoring

---

## Author

Siddhanth Gowda

