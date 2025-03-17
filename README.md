# Counterparty Portfolio Loss under the Merton Asset Value Model

## 1. Introduction
Counterparty credit risk is a key concern for financial institutions, especially in derivatives trading and loan portfolios. The Merton Asset Value Model provides a structural approach to estimating default probabilities by modeling a firm's asset dynamics. This document extends the model to a portfolio of counterparties to estimate overall portfolio loss.

## 2. The Merton Asset Value Model

### 2.1 Basic Assumptions
- A firm's asset value \( V_t \) follows a **Geometric Brownian Motion (GBM)**:
  \[
  dV_t = \mu V_t dt + \sigma V_t dW_t
  \]
- The firm has debt \( D \) due at time \( T \).
- Default occurs when \( V_T < D \).
- The probability of default (PD) is given by:
  \[
  PD = \Phi(-d_2)
  \]
  where \( \Phi \) is the cumulative normal distribution function, and:
  \[
  d_2 = \frac{\ln(V_0 / D) + (\mu - 0.5\sigma^2)T}{\sigma\sqrt{T}}
  \]

### 2.2 Portfolio Extension
For a **portfolio of N counterparties**, each with assets \( V_i \) and debt \( D_i \), we consider:
- **Correlated asset dynamics**, modeled via a **Gaussian Copula**.
- Systematic (market-wide) and idiosyncratic (firm-specific) risk factors.
- Dependence between counterparties based on industry or macroeconomic conditions.

## 3. Portfolio Loss Calculation

### 3.1 Expected Loss (EL)
The total expected loss for the counterparty portfolio is:
\[
EL = \sum_{i=1}^{N} EAD_i \times LGD_i \times PD_i
\]
where:
- \( EAD_i \) = Exposure at Default for counterparty \( i \)
- \( LGD_i \) = Loss Given Default (fraction of exposure lost)
- \( PD_i \) = Probability of Default from the Merton model

### 3.2 Monte Carlo Simulation for Portfolio Loss
Given the **correlation structure** between counterparties, we:
1. Simulate **joint asset paths** for all counterparties using correlated GBM processes.
2. Determine **which firms default** based on the debt threshold \( D_i \).
3. Compute **portfolio loss** as the sum of individual losses.

## 4. Practical Implementation

### 4.1 Steps
1. **Data Collection:** Gather asset values, debt levels, volatilities, and correlations.
2. **Estimate Default Probabilities:** Use the Merton model to compute \( PD_i \) for each counterparty.
3. **Simulate Portfolio Loss:** Run Monte Carlo simulations to estimate the loss distribution.
4. **Analyze Results:** Compute expected and unexpected loss, considering regulatory capital requirements.

## 5. Conclusion
- The Merton model provides an analytical framework for counterparty risk assessment.
- Portfolio-level loss estimati
