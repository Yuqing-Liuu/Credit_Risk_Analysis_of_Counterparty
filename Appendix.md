# Appendix A. Python Monte Carlo Simulation Code

## A.1 Overview

This appendix provides the Python implementation of the Monte Carlo simulation framework developed in Chapter IV.  
The program simulates correlated short-rate and credit-spread processes, generates exposure paths, and computes key metrics including Expected Exposure (EE), Expected Positive Exposure (EPE), and Credit Valuation Adjustment (CVA).  

The model follows the structure:

$$
CVA = (1 - R) \sum_{k=1}^{K} DF(t_k) \times EE(t_k) \times \Delta PD(t_k)
$$

where \( R \) is the recovery rate, \( DF(t_k) \) are the discount factors, \( EE(t_k) \) represents expected exposures, and \( \Delta PD(t_k) \) denotes default probability increments.

---

## A.2 Implementation Code (Python)

```python
import numpy as np
import pandas as pd

# Monte Carlo parameters
N = 10000      # number of simulated paths
K = 50         # time steps (quarterly)
T = 12.5       # total horizon in years
dt = T / K

# Model parameters
a, b, sigma_r = 0.05, 0.03, 0.01     # Hull-White rate parameters
sigma_s, rho = 0.015, 0.25           # credit spread volatility and correlation
R, spread0 = 0.40, 0.008             # recovery rate and initial credit spread

# Generate correlated Brownian motions
Z1 = np.random.normal(size=(N, K))
Z2 = np.random.normal(size=(N, K))
W_r = Z1
W_s = rho * Z1 + np.sqrt(1 - rho**2) * Z2

# Initialize short rate (r) and credit spread (s)
r = np.zeros((N, K))
s = np.zeros((N, K))

for k in range(1, K):
    r[:, k] = r[:, k-1] + a * (b - r[:, k-1]) * dt + sigma_r * np.sqrt(dt) * W_r[:, k]
    s[:, k] = s[:, k-1] + 0.3 * (spread0 - s[:, k-1]) * dt + sigma_s * np.sqrt(dt) * W_s[:, k]

# Discount factors
df = np.exp(-np.cumsum(r, axis=1) * dt)

# Simulate portfolio exposure
exposure = np.maximum(0.5 * np.random.randn(N, K) * np.exp(-0.5 * r), 0)

# Compute Expected Exposure (EE)
EE = exposure.mean(axis=0)
EPE = EE.mean()

# Hazard rate and default probability
hazard = s.mean(axis=0) / (1 - R)
PD = 1 - np.exp(-np.cumsum(hazard) * dt)

# CVA estimation
CVA = (1 - R) * np.sum(df.mean(axis=0) * EE * np.diff(np.insert(PD, 0, 0)))

print("Expected Positive Exposure (EPE):", round(EPE, 4))
print("Credit Valuation Adjustment (CVA):", round(CVA, 4))

