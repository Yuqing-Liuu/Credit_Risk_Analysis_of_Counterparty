# Chapter 6 Conclusions and Prospects

## 6.1 Conclusions

This study developed an integrated framework for counterparty credit risk assessment by combining the KMV structural model with GARCH-based volatility dynamics. Applying this framework to major U.S. financial institutions over the 2018–2024 period yielded several significant findings.

The empirical results confirm that Distance to Default effectively differentiates solvency positions across institutions. Well-capitalized banks with lower equity volatility—such as JPMorgan Chase and PNC Financial—consistently exhibited higher DD values and greater financial resilience, while smaller or more leveraged counterparties displayed narrower safety margins. This validates DD as a real-time, market-responsive indicator that bridges traditional balance-sheet metrics and forward-looking market assessments.

The analysis also demonstrates a robust inverse relationship between equity volatility and DD. Elevated market volatility directly compresses default distances, reflecting heightened uncertainty regarding asset values. This finding underscores the importance of embedding dynamic volatility processes into CCR measurement frameworks to capture time-varying risk that static models overlook.
From a practical perspective, the KMV-GARCH metrics can be operationalized within institutional risk management infrastructures. The proposed quantile-based classification system enables dynamic adjustment of counterparty exposures, aligning internal risk limits with continuously updating market signals. Portfolio-level DD distributions also provide supervisory authorities with systemic perspectives on sectoral solvency, supporting early-warning mechanisms under Basel III.
The framework demonstrates that properly calibrated market information serves as a valuable complement to traditional credit analysis and regulatory capital measurement. By providing both institution-specific and systemic risk insights, the model contributes to a more responsive and empirically grounded approach to counterparty credit risk management in modern financial institutions.

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

