## Modeling CVA Risk

## 1. Introduction
1.1 Background and Motivation

    The global financial crisis of 2008 exposed major weaknesses in how banks measured and managed counterparty credit risk (CCR). Losses from the default of large financial institutions such as Lehman Brothers showed that credit exposure in over-the-counter (OTC) derivatives was underestimated (Gregory, 2015). In response, regulators under the Basel Committee on Banking Supervision (BCBS) introduced new rules to improve risk measurement and capital adequacy. A key component of these reforms was the Credit Valuation Adjustment (CVA), which represents the adjustment to the fair value of derivative positions to account for the possibility that a counterparty may default before contract maturity (BCBS, 2011).

    CVA connects credit and market risk, as it depends on both the exposure profile of the trade and the credit quality of the counterparty. Understanding and accurately estimating this adjustment has become a crucial part of modern risk management. Moreover, financial institutions are now required to hold additional capital for CVA risk, reflecting the potential volatility of credit spreads. This has increased the importance of developing accurate, simulation-based methods for measuring exposure and its mitigation through netting and collateralization.

1.2 Research Problem and Objectives

    Despite the regulatory advances, measuring counterparty credit exposure remains a complex challenge. Simplified methods such as the Current Exposure Method (CEM) or the Standardized Approach for Counterparty Credit Risk (SA-CCR) often overestimate exposure because they use fixed regulatory parameters and ignore portfolio effects such as netting or collateral. In contrast, the Internal Model Method (IMM) allows banks to estimate exposures using Monte Carlo simulation, which models the stochastic evolution of market risk factors and provides a more accurate representation of exposure over time (BCBS, 2015).

    The main objective of this thesis is to develop a Monte Carlo simulation framework to estimate counterparty credit exposure under realistic market and credit conditions. The framework incorporates netting and collateral agreements as defined by the ISDA Master Agreement and Credit Support Annex (CSA). The study aims to show how these risk mitigants influence the exposure profile and, consequently, the CVA value. By comparing simulation-based results with standardized regulatory methods, the thesis seeks to highlight the advantages and limitations of each approach in practical risk management.

1.3 Scope and Limitations

    This research focuses on the estimation of exposure for derivative portfolios, particularly interest rate swaps, which are commonly used instruments in counterparty risk studies. The analysis is based on simulated market data rather than actual bank portfolios, allowing flexibility in exploring different risk drivers and stress scenarios.

    The thesis does not include the estimation of other valuation adjustments such as Debit Valuation Adjustment (DVA), Funding Valuation Adjustment (FVA), or Capital Valuation Adjustment (KVA). The scope is limited to the modeling of CVA and the impact of contractual risk mitigants. Furthermore, model validation and backtesting against real market data are beyond the scope of this work, although the results can serve as a conceptual foundation for future empirical studies.

---

## 2. Literature Review and Theoretical Background
- 2.1 Overview of Counterparty Credit Risk (CCR)  
- 2.2 The Evolution of the Basel Regulatory Framework  
- 2.3 The Concept of Credit Valuation Adjustment (CVA)  
- 2.4 Key Components: Exposure, PD, LGD, and EAD  
- 2.5 Netting and Collateralization under ISDA and CSA Agreements  
- 2.6 Modeling Challenges: Wrong-Way Risk and Dependency Structures  
- 2.7 Summary  

---

## 3. Regulatory Framework for CVA Capital Charge
- 3.1 Basel II: Early Treatment of Counterparty Credit Risk  
- 3.2 Basel III: Introduction of CVA Capital Charge  
- 3.3 Comparison of Regulatory Approaches  
  - 3.3.1 Current Exposure Method (CEM)  
  - 3.3.2 Standardized Approach (SA-CCR)  
  - 3.3.3 Internal Model Method (IMM)  
- 3.4 Regulatory Evolution under Basel IV  
- 3.5 Practical Challenges in Regulatory Implementation  
- 3.6 Summary  

---

## 4. Methodology
- 4.1 Modeling Counterparty Credit Exposure  
- 4.2 Monte Carlo Simulation Framework  
- 4.3 Stochastic Models for Market Risk Factors  
  - 4.3.1 Interest Rate Models  
  - 4.3.2 Credit Spread Models  
- 4.4 Exposure Metrics: EE, EPE, and PFE  
- 4.5 Integration of Netting and Collateral Adjustments  
- 4.6 Calculation of Credit Valuation Adjustment (CVA)  
- 4.7 Implementation Design and Simulation Parameters  

---

## 5. Simulation and Results
- 5.1 Data Inputs and Assumptions  
- 5.2 Portfolio Composition and Trade Characteristics  
- 5.3 Simulation of Exposure Profiles  
- 5.4 Impact Analysis  
  - 5.4.1 Netting Effects  
  - 5.4.2 Collateralization and Thresholds  
  - 5.4.3 Credit Rating Deterioration  
- 5.5 Comparative Analysis: IMM vs CEM  
- 5.6 Stress Testing and Sensitivity Analysis  
- 5.7 Discussion of Results  

---

## 6. Conclusion and Future Work
- 6.1 Summary of Findings  
- 6.2 Key Insights on IMM vs CEM  
- 6.3 Implications for Risk Management and Regulation  
- 6.4 Limitations of the Study  
- 6.5 Recommendations for Future Research  

---




