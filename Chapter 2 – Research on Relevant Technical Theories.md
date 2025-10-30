# Chapter 2 Research on Relevant Technical Theories  

## 2.1 Credit Risk Management Theory  

### 2.1.1 Asset Management Theory  

The concept of asset management theory originates from the early stage of commercial banking development. Its core idea is that the primary function of a bank is to manage its assets to maximize profits while ensuring sufficient liquidity. In this framework, banks mainly focus on the structure and efficiency of their asset portfolios. By properly allocating funds among loans, securities, and reserves, banks seek to achieve the balance between liquidity, safety, and profitability.  

However, with the increasing complexity of financial markets, the focus of asset management gradually shifted from simple portfolio optimization to a more comprehensive risk-based approach. Counterparty credit risk became an important component of this framework. The measurement and control of counterparty credit risk involve assessing the possibility of default by the transaction partner and quantifying potential losses in case of default (*Duffie 2003; Basel Committee on Banking Supervision 2006*).  

Under asset management theory, the optimization of credit portfolios requires quantitative evaluation models. Among these models, the **KMV model** and the **Value at Risk (VaR)** methodology are often applied to assess credit-exposure volatility and the probability of default (*Pykhtin and Zhu 2006*). This evolution has provided a theoretical foundation for modern financial institutions to integrate market-risk and credit-risk management.

### 2.1.2 Liability Management Theory  

Liability management theory emerged in the 1960s as financial markets developed and deposit volatility increased. The theory argues that banks can actively manage both sides of the balance sheet — assets and liabilities — to achieve liquidity control. Instead of passively relying on deposit inflows, banks can obtain funding from the money market to support credit expansion.  

In the context of counterparty credit risk, liability management implies that a financial institution should not only manage the risk of default from its borrowers but also the risk from its own funding sources. When a bank’s liability structure becomes unstable, counterparty exposures can amplify systemic risk. Therefore, liability management theory emphasizes comprehensive monitoring of short-term borrowing, interbank financing, and derivative obligations (*Gibson 2005; Basel Committee on Banking Supervision 2011*).  

Together, asset and liability management theories constitute the theoretical foundation for integrated credit-risk management in modern financial institutions. They provide the conceptual basis for quantitative models such as the KMV model used later in this study.

---

## 2.2 KMV Model  

### 2.2.1 Theoretical Overview  

The KMV model, developed by KMV Corporation in the 1990s and later acquired by Moody’s, is based on **Merton’s option-pricing theory**. It applies the concept of corporate assets as underlying variables and liabilities as strike prices to estimate the probability of default. The model assumes that a company defaults when the market value of its assets falls below its debt obligations at maturity (*Duffie 2003*).  

Mathematically, the model can be summarized as follows:

Let  
- \( V_A \) = market value of firm assets,  
- \( D \) = debt value (default point),  
- \( \sigma_A \) = asset volatility,  
- \( T \) = time horizon.

The **distance to default (DD)** is given by  

\[
DD = \frac{\ln(V_A / D) + (r - 0.5\sigma_A^2)T}{\sigma_A \sqrt{T}}
\]

and the **expected default frequency (EDF)** is derived as  

\[
EDF = N(-DD)
\]

where \( N(\cdot) \) is the cumulative normal distribution function.  

The advantage of the KMV model lies in its ability to estimate forward-looking default probabilities based on market information rather than accounting data. It links credit-risk measurement with option pricing, providing a bridge between market-risk and credit-risk disciplines (*Brigo and Capponi 2010; Pykhtin and Zhu 2006*).

### 2.2.2 Research Method of KMV Model  

The implementation of the KMV model generally includes the following steps:  

1. **Estimation of asset value and volatility.**  
   The model treats a firm’s equity as a call option on its assets with strike price equal to the face value of debt. Using the Black-Scholes option formula, the market value and volatility of the firm’s assets can be estimated iteratively from observed equity prices and debt data.  

2. **Determination of the default point.**  
   The default point \( D \) is typically defined as the sum of short-term liabilities and half of long-term liabilities. This definition approximates the level at which a firm is expected to default.  

3. **Computation of distance to default (DD) and expected default frequency (EDF).**  
   Once asset value and volatility are estimated, the DD and EDF can be calculated using the formulas above. The EDF is a key indicator of a firm’s credit quality.  

4. **Empirical validation.**  
   Empirical studies (*Lu and Juan 2011; Gibson 2005*) confirm that KMV-derived default probabilities correlate closely with actual default rates, supporting the model’s predictive effectiveness.  

The KMV model has been widely adopted by commercial banks and investment institutions to assess counterparty credit risk and to determine capital requirements under Basel II and Basel III frameworks (*Basel Committee on Banking Supervision 2006; Basel Committee on Banking Supervision 2011*).  

---

## Summary of Chapter 2  

This chapter reviewed the theoretical foundation of credit-risk management, focusing on **asset management**, **liability management**, and the **KMV model**. Together, these theories provide the analytical tools necessary to understand counterparty credit risk. Asset and liability management explain how financial institutions structure their portfolios and funding sources to balance liquidity and profitability, while the KMV model offers a quantitative approach to estimating default probabilities using market data.  

These theoretical foundations establish the basis for the next chapter, which will apply these models to measure counterparty credit risk through comparative analysis and empirical estimation.
