# Chapter 2 Research on Relevant Technical Theories

## 2.1 Credit Risk Management Theory

### 2.1.1 Asset Management Theory

The theory of asset management emerged during the early development of modern commercial banking. Its fundamental assumption is that a bank’s core objective is to manage assets efficiently so as to maximise profit while maintaining adequate liquidity. Under this framework, financial institutions allocate funds among loans, securities and reserves in a way that balances liquidity, safety and profitability.

As financial markets evolved, banks increasingly faced complex risks associated with interest-rate fluctuations, exchange-rate volatility and counterparty defaults. The traditional concept of passive asset allocation thus shifted toward active portfolio management and risk-based capital regulation. Counterparty credit risk became an important component of this transformation, as it directly affects a bank’s exposure to derivative and financing transactions (Duffie 2003; Basel Committee on Banking Supervision 2006).

The modern interpretation of asset-management theory emphasises the integration of market-risk and credit-risk management. Quantitative methods such as the KMV model and the Value-at-Risk (VaR) approach are used to measure the volatility of asset portfolios and to estimate the probability of default (Pykhtin and Zhu 2006). These developments have provided a scientific foundation for banks to evaluate counterparty exposures and to maintain stability within the financial system.

In addition to international contributions, Chinese scholars have elaborated on the adaptation of asset-management theory within domestic financial institutions. Their work has stressed that banks should strengthen credit-evaluation mechanisms, classify counterparties by risk level and dynamically adjust lending and derivative exposure according to market signals. Such approaches reflect the gradual convergence of Chinese banking practices with global risk-management standards.

### 2.1.2 Liability Management Theory

Liability-management theory originated in the 1960s as financial institutions began to diversify funding sources beyond customer deposits. The theory suggests that banks can actively manage both sides of the balance sheet—assets and liabilities—to ensure liquidity and profitability. Instead of passively waiting for deposit inflows, banks can access wholesale-funding markets, issue short-term instruments and use derivatives to hedge funding risks.

In relation to counterparty credit risk, liability management underscores the interdependence between funding stability and credit exposure. A bank with an unstable liability structure may amplify systemic risk when counterparties simultaneously withdraw funding or default. Therefore, this theory calls for comprehensive monitoring of interbank borrowing, securities financing and derivative obligations (Gibson 2005; Basel Committee on Banking Supervision 2011).

In the Chinese context, scholars have argued that domestic banks often rely excessively on deposit-based funding and lack diversified liability structures. To align with international standards, they have proposed the introduction of dynamic-liability-management systems that incorporate market-based instruments, capital-market borrowing and liquidity buffers. This evolution will help Chinese banks mitigate counterparty risks associated with concentrated short-term liabilities.

Asset management and liability management together form the theoretical foundation of integrated credit-risk management. They provide both the conceptual and methodological basis for quantitative models such as the KMV framework, which will be applied in subsequent chapters.

---

## 2.2 KMV Model

### 2.2.1 Theoretical Overview

The KMV model was developed by KMV Corporation in the 1990s and later acquired by Moody’s Analytics. It is derived from Merton’s option-pricing theory, which treats a company’s equity as a call option on its total assets with the strike price equal to the face value of debt. Default occurs when the market value of the firm’s assets falls below its debt obligations at maturity (Duffie 2003).

Let  

- \( V_A \) denote the market value of assets,  
- \( D \) denote the book value of debt (default point),  
- \( \sigma_A \) denote the asset volatility, and  
- \( T \) denote the time horizon.

The distance to default (DD) is expressed as

$$
DD = \frac{\ln(V_A / D) + (r - 0.5\sigma_A^2)T}{\sigma_A \sqrt{T}}
$$

and the expected default frequency (EDF) is derived as

$$
EDF = N(-DD)
$$

where \( N(x) \) denotes the cumulative normal distribution function.

The KMV model’s advantage lies in its ability to infer default probabilities directly from market data rather than from accounting information. It links credit-risk measurement with option-pricing theory, thus bridging the gap between market and credit risk (Brigo and Capponi 2010; Pykhtin and Zhu 2006).

Chinese researchers have also explored the KMV framework in domestic markets. Their studies have shown that market-value-based models can be applied to evaluate listed companies’ default risk, though such applications face challenges due to incomplete data disclosure and market inefficiencies. These findings highlight the importance of developing local calibration techniques that account for regional financial characteristics.

### 2.2.2 Research Method of KMV Model

The practical implementation of the KMV model generally involves the following steps.

1. **Estimation of asset value and volatility**  
   The firm’s equity is treated as a call option on its assets, and the Black–Scholes option model is used to estimate the market value and volatility of assets through iterative calculations. Market-equity value and volatility are observable, whereas asset parameters are derived endogenously.

2. **Determination of the default point**  
   The default point \( D \) is typically defined as the sum of short-term liabilities and half of long-term liabilities. This reflects the level of total obligations that may trigger default under adverse conditions.

3. **Computation of distance to default and expected default frequency**  
   Once \( V_A \) and \( \sigma_A \) are obtained, the DD and EDF are computed using the formulas above. The EDF serves as a forward-looking indicator of default probability.

4. **Empirical validation**  
   Empirical analyses conducted by both international and domestic researchers (Lu and Juan 2011; Gibson 2005) have demonstrated a strong correlation between KMV-estimated EDF values and actual default rates. This confirms the model’s predictive accuracy and practical relevance.

In Chinese studies, researchers have tested the KMV model using samples of listed manufacturing and financial companies. They have found that the model captures relative differences in credit quality but that calibration of asset volatility remains sensitive to market conditions. Consequently, some scholars have proposed combining the KMV framework with GARCH models to improve volatility estimation and enhance EDF precision.

The KMV model has now become one of the most widely used approaches for default-probability estimation and credit-risk evaluation in global banking practice. It also serves as an important reference for capital-requirement calculations under Basel II and Basel III (Basel Committee on Banking Supervision 2006; Basel Committee on Banking Supervision 2011).

---

## Summary of Chapter 2

This chapter introduced the theoretical foundation of counterparty credit-risk analysis. Asset-management and liability-management theories explain how financial institutions maintain a balance between liquidity, profitability and solvency, while the KMV model provides a quantitative tool to measure default probability using market-based information.

International and domestic studies both affirm that effective CCR management depends on integrating qualitative judgement with quantitative modelling. In particular, Chinese research has begun to adapt models such as KMV to local market environments, contributing to the broader understanding of credit-risk management in emerging economies.

The next chapter will extend these theoretical insights to construct specific measurement models for counterparty credit risk and to compare their empirical implications.
