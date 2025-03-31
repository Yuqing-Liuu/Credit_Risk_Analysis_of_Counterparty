## Modeling CVA Risk

### Introduction
This thesis provides an overview of Credit Valuation Adjustment (CVA) and related concepts within the context of counterparty credit risk. It begins by outlining the historical events that led to the reform of the Basel regulatory framework and the incorporation of CVA as a key component of counterparty risk management.

After establishing the conceptual foundations, the thesis explores the regulatory treatment of CVA in detail. It introduces the three most widely used methods for calculating the regulatory CVA capital charge, addressing their underlying principles and practical challenges. A particular focus is placed on two methods: the Internal Model Method (IMM) and the Current Exposure Method (CEM). Their differences are examined both conceptually and mathematically.

To support the analysis, the thesis includes simulation-based comparisons using portfolios of interest rate swaps with varying maturities and counterparties of differing credit quality. The results highlight the central importance of CVA in managing counterparty credit risk and demonstrate the strengths of IMM, particularly its ability to better reflect market reality compared to CEM.

### Data (interest rate sawps)
* Swap Portfolio – e.g., 10–20 interest rate swap contracts with:

* Yield Curve – e.g., a simple bootstrapped curve from deposit/swap rates

* Forward Curve – derived from yield curve (or flat forward rates for simplicity)

* Credit Spread Curve – for counterparties with different ratings (A, BBB, etc.)

* Recovery Rate

### Technology
Python
