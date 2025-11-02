# Chapter 6 Conclusions and Prospects

## 6.1 Conclusions

This study developed an integrated framework for assessing counterparty credit risk (CCR) based on the GARCH–KMV model, combining market-based volatility dynamics with structural default modeling.  
By applying the framework to a representative sample of major U.S. banks over the 2018–2024 period, the analysis produced several meaningful conclusions.

First, the empirical findings demonstrate that the **Distance to Default (DD)** effectively captures differences in solvency across institutions.  
Banks with higher capitalization and lower equity volatility—such as JPMorgan Chase and PNC—showed greater resilience, while smaller or more leveraged institutions exhibited narrower safety buffers.  
This highlights DD’s value as a real-time indicator of financial stability, bridging the gap between traditional accounting metrics and market-based assessments.

Second, the results confirm the strong **inverse relationship between equity volatility and DD**.  
Institutions with elevated market volatility tend to have shorter distances to default, indicating that changes in investor sentiment and market uncertainty directly translate into higher counterparty risk.  
This relationship underscores the importance of incorporating dynamic volatility modeling (via GARCH processes) into CCR measurement frameworks.

Third, from a management perspective, the study shows that the KMV-based metrics can be operationalized to enhance **internal risk control** and **regulatory monitoring**.  
Through quantile-based classification, counterparty exposures can be prioritized and adjusted dynamically, aligning internal risk limits with real-time market information.  
Moreover, the DD distribution provides a systemic view of sectoral solvency that can inform supervisory early-warning systems under Basel III.

Overall, the GARCH–KMV model demonstrates that market information—when properly structured and calibrated—can serve as a reliable complement to traditional credit analysis and regulatory capital measurement.  
It enables both micro-level (institutional) and macro-level (systemic) insights, contributing to a more responsive and data-driven approach to counterparty credit risk management.

## 6.2 Limitations and Outlook

Although the findings are encouraging, several limitations should be acknowledged.  
First, the analysis relies on publicly available market data (equity prices, balance-sheet items, and Treasury yields), which may not capture private exposures, off-balance-sheet derivatives, or intraday market dynamics.  
Future work could incorporate more granular datasets—such as counterparty-level exposure records or transaction-based repo data—to refine model precision.

Second, the **KMV structural assumptions** impose certain simplifications.  
For instance, the default point is approximated as a weighted sum of short- and long-term debt, while asset values are inferred rather than observed.  
Alternative structural or reduced-form models, such as the Merton–Jump Diffusion or Copula-based approaches, may capture nonlinear dependence and tail risk more effectively.

Third, the **GARCH(1,1)** specification, though standard, may not fully capture volatility clustering during extreme market events.  
Future research could extend this framework using asymmetric or regime-switching GARCH models to account for volatility asymmetry and contagion effects.

Finally, while this study focuses on U.S. banks, the model’s applicability could be broadened through **cross-country comparative analysis**.  
Examining the DD distribution across different regulatory regimes—such as European or Asian markets—would help assess the universality and robustness of the GARCH–KMV approach.

In conclusion, this research provides a methodological and empirical foundation for incorporating market-based models into counterparty credit risk assessment.  
Further extensions that integrate high-frequency data, advanced volatility structures, and cross-market calibration can contribute to a more adaptive and forward-looking framework for both practitioners and regulators in the evolving landscape of financial risk management.

