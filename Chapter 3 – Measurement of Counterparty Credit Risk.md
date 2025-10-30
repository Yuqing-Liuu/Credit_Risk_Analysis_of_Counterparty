# Chapter 3 Measurement of Counterparty Credit Risk

## 3.1 Basic Overview of Counterparty Credit Risk

Counterparty credit risk (CCR) refers to the potential loss a financial institution faces when a counterparty in a derivatives or securities-financing transaction defaults before the final settlement of cash flows. Unlike traditional loan credit risk, CCR depends on the market value of the underlying transaction, which can fluctuate over time and may even become negative.

The emergence of CCR is mainly related to the expansion of derivative products. Before the 2008 global financial crisis, banks and investment institutions relied heavily on complex instruments such as credit default swaps (CDS) and collateralized debt obligations (CDOs). When systemic risk intensified, these exposures caused large-scale contagion effects in financial markets (Duffie 2003). Therefore, the accurate measurement of CCR has become a key component of risk management and capital regulation (Basel Committee on Banking Supervision 2006).

### 3.1.1 Evolution of Measurement Models

The earliest measurement of CCR was based on a static current-exposure approach, focusing only on present positive market values of contracts. Over time, the industry developed dynamic simulation models that estimate future exposure distributions over time (Pykhtin and Zhu 2006). The main evolution stages include:

1. **Current Exposure Method (CEM)** – A simple, add-on-based approach that calculates CCR as the sum of current exposure and a potential future exposure (PFE) add-on.  
2. **Standardized Method (SM)** – Introduced under Basel II, this method adjusts exposures by product category and counterparty type.  
3. **Internal Model Method (IMM)** – Allows banks to use internal simulation models to compute expected exposure profiles.  
4. **Non-Internal Model Method (NIMM)** – Introduced in Basel III to replace IMM in some cases, providing a simplified standardized approach with regulatory calibration.

Each stage reflects the Basel Committee’s effort to balance simplicity, comparability, and risk sensitivity in CCR measurement.

### 3.1.2 Measurement of Credit Risk

Credit risk measurement typically involves two main variables: **exposure** and **probability of default (PD)**. For counterparty credit risk, exposure is stochastic and depends on future market factors. The expected exposure at time \(t\) can be defined as:

$$
EE_t = E[\max(V_t, 0)]
$$

where \(V_t\) is the future market value of the transaction. The expected positive exposure (EPE) over the lifetime of the contract is the time-weighted average of \(EE_t\):

$$
EPE = \frac{1}{T} \int_0^T EE_t \, dt
$$

The counterparty credit risk capital charge is generally proportional to EPE multiplied by the loss given default (LGD) and the default probability over the exposure horizon (Basel Committee on Banking Supervision 2011).

---

## 3.2 Measurement Models of Counterparty Credit Risk

### 3.2.1 Current Exposure Method (CEM)

The Current Exposure Method, proposed under Basel I and maintained in Basel II, measures exposure as the sum of the current mark-to-market (MtM) value of all contracts with positive replacement cost and an add-on for potential future exposure.

$$
EAD = RC + AddOn
$$

where \(RC\) represents the current positive replacement cost and \(AddOn\) is a percentage of the notional principal amount based on the contract type and maturity.  

Although simple and transparent, CEM tends to overestimate exposure for long-term or collateralized transactions because it ignores netting and margining effects (Gibson 2005).

### 3.2.2 Internal Model Method (IMM)

The Internal Model Method allows banks to estimate exposure through Monte Carlo simulations of future market scenarios. The model computes the expected exposure (EE) and expected positive exposure (EPE) for each counterparty based on simulated price paths (Pykhtin and Zhu 2006).

Formally, the effective expected positive exposure (EEPE) is given by:

$$
\mathrm{EEPE}=\frac{1}{T^{\ast}}\int_{0}^{T^{\ast}} \max(EE_t,\,0)\,dt
$$

where \(T^{\ast}\) is the effective maturity of the portfolio. The IMM requires supervisory approval and extensive back-testing to validate the accuracy of exposure estimation models.

### 3.2.3 Standardized Method (SM)

The Standardized Method, introduced under Basel II and refined in Basel III, calculates CCR exposure using standardized supervisory parameters. The exposure at default (EAD) is determined as:

$$
EAD = \alpha \times (RC + PFE)
$$

where \(\alpha\) is a regulatory scaling factor (typically 1.4). PFE is derived from a regulatory schedule based on asset class and maturity. The method simplifies the capital-calculation process but may lack risk sensitivity for complex portfolios (Basel Committee on Banking Supervision 2006).

### 3.2.4 Non-Internal Model Method (NIMM)

The Non-Internal Model Method, proposed by the Basel Committee (2011), aims to address the shortcomings of IMM while reducing implementation costs. It incorporates standardized supervisory factors for each asset class and accounts for margining, netting, and collateralization effects.

Under NIMM, exposure is computed using a risk-sensitivity-based formula similar to the standardized approach used in the Fundamental Review of the Trading Book (FRTB). NIMM enhances transparency and comparability across institutions and serves as the default approach for CCR under Basel III.

---

## 3.3 Measurement of Central Counterparty Credit Risk

### 3.3.1 Capital Requirement Model

Central counterparties (CCPs) play a key role in mitigating bilateral counterparty risk by acting as intermediaries in cleared transactions. However, CCPs themselves face systemic credit exposure when a clearing member defaults (Brigo and Capponi 2010).

The capital requirement for exposures to a qualifying CCP (QCCP) can be calculated as:

$$
K_{CCP} = \sum_i w_i \times EAD_i
$$

where \(EAD_i\) is the exposure to the i-th clearing member and \(w_i\) is a risk weight determined by the CCP’s regulatory status and financial soundness.

Non-qualifying CCPs are subject to higher capital charges. The regulatory framework ensures that banks maintain sufficient capital to absorb losses from CCP defaults while still benefiting from reduced bilateral exposure through central clearing.

### 3.3.2 Latest Measurement Models

Recent research has integrated credit valuation adjustment (CVA) and wrong-way risk into CCR capital frameworks. Wrong-way risk occurs when exposure to a counterparty increases simultaneously with the probability of its default (Brigo and Masetti 2005). Advanced simulation methods, such as the Monte Carlo and copula-based approaches, are used to model the joint distribution of market and credit factors.

Furthermore, stress testing and scenario analysis have become mandatory components of CCR measurement. These techniques assess the sensitivity of exposures to extreme market events, enhancing the resilience of financial institutions against systemic shocks (Basel Committee on Banking Supervision 2011).

---

## Summary of Chapter 3

This chapter introduced various methods for measuring counterparty credit risk. The development of CCR measurement has evolved from the simple Current Exposure Method (CEM) to the Internal Model Method (IMM), Standardized Method (SM), and Non-Internal Model Method (NIMM). Each approach represents a trade-off between accuracy and operational complexity.

The chapter also discussed capital requirements for central counterparties and the integration of CVA, wrong-way risk, and stress testing into modern frameworks. These developments form the foundation for the empirical analysis presented in the following chapter, which applies the discussed models to estimate counterparty credit exposures and assess their implications for risk-weighted assets.

