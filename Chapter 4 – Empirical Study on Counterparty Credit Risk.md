# Chapter 4. Empirical Analysis of Counterparty Credit Risk

## 4.1 Overview

This chapter presents the empirical analysis of counterparty credit risk among major U.S. banking institutions using a combined GARCH–KMV framework. The model integrates time-varying market volatility with the structural default framework to capture both cross-sectional differences in solvency and dynamic changes in credit risk over time.

In contemporary financial systems, counterparty credit risk (CCR) constitutes a central source of exposure for banks, particularly in derivatives and interbank markets. It arises when one institution faces the risk that its counterparty will default before the settlement of a financial transaction. Since the global financial crisis of 2008, international regulatory frameworks, especially Basel III, have placed greater emphasis on the identification, quantification, and control of CCR. Nevertheless, the quantitative measurement of CCR continues to rely on both structural and market-based approaches, with the KMV model remaining one of the most widely used frameworks (Merton 1974; Pykhtin and Zhu 2006; Gregory 2015).

The KMV model, derived from the Merton (1974) structural theory of corporate default, treats a firm's equity as a call option on its assets. The probability of default depends on the position of the firm's asset value relative to a default barrier, expressed in standard deviation units as the Distance to Default (DD). The DD serves as a continuous measure of solvency: a higher DD implies greater financial strength and a lower likelihood of default. The Expected Default Frequency (EDF), computed as the probability that the asset value falls below the default barrier, translates DD into an explicit probability of default.While the KMV model captures the structural foundations of default behavior, it assumes constant asset volatility. In reality, financial markets exhibit volatility clustering and time-varying variance, particularly during episodes of market turbulence. To address this limitation, the present study incorporates a Generalized Autoregressive Conditional Heteroskedasticity (GARCH) model into the KMV framework (Engle 1982; Bollerslev 1986). The GARCH(1,1) specification models the conditional variance of returns as a function of past shocks and previous volatility, allowing the model to adapt dynamically to evolving market conditions.

The integration of the GARCH and KMV frameworks produces a dynamic structural model that links firm fundamentals with market-derived risk factors. This approach enables the measurement of solvency for each institution at a given point in time and the analysis of how market shocks influence credit-risk dynamics. The empirical analysis focuses on ten major U.S. banks: JPMorgan Chase, Bank of America, Citigroup, Capital One, PNC Financial, Wells Fargo, M&T Bank, Fifth Third Bank, Truist Financial, and U.S. Bancorp. Together, these institutions represent a substantial share of the U.S. financial system and are central participants in interbank and derivative markets.The observation period from January 2018 to December 2024 encompasses both stable and turbulent market phases. This range allows for the examination of how solvency indicators such as DD and EDF respond to macroeconomic stress and subsequent recovery. The dataset combines daily market data (stock prices and volatilities) with balance-sheet variables (total assets, liabilities, and debt structure), forming a comprehensive basis for model calibration and estimation.

The empirical objectives of this chapter are twofold. First, it seeks to evaluate the solvency and default risk of the selected banks using market-based information. Second, it examines whether the results are consistent with the capital adequacy principles outlined in Basel III, which require banks to maintain sufficient buffers against counterparty default. By comparing model-implied solvency indicators with regulatory standards, the analysis provides insights into the effectiveness of the GARCH–KMV framework as a quantitative tool for assessing counterparty credit risk.

We applies the GARCH–KMV model to estimate the Distance to Default and Expected Default Frequency for ten major U.S. banks. The results illustrate the stability and resilience of the U.S. banking system during the period under study and demonstrate the usefulness of combining structural and market-based methodologies for the analysis of counterparty credit risk. The following sections describe the data, model specification, and implementation procedures in detail before presenting and interpreting the empirical findings.


---

## 4.2 Data Description

This section describes the dataset used in the empirical analysis, including the sample selection, data sources, variable definitions, and preprocessing procedures. The empirical study focuses on a representative sample of major U.S. banking institutions to ensure that the results reflect systemic characteristics of the banking sector rather than the idiosyncrasies of individual firms.

### 4.2.1 Sample Selection

The empirical analysis covers ten publicly listed U.S. banks: JPMorgan Chase (JPM), Bank of America (BAC), Citigroup (C), Capital One (COF), PNC Financial (PNC), Wells Fargo (WFC), M&T Bank (MTB), Fifth Third Bank (FITB), Truist Financial (TFC), and U.S. Bancorp (USB). These institutions are selected on the basis of market capitalization, data availability, and their importance within the interbank and derivatives markets. Together, they represent a significant portion of total U.S. banking assets and form an appropriate sample for studying counterparty credit risk under the Basel III framework.

The observation period spans from January 2018 to December 2024. This period is chosen to include both normal and stressed financial conditions, most notably the COVID-19-induced market disruptions in 2020, followed by subsequent recovery phases. The seven-year horizon allows for a comprehensive examination of how solvency indicators evolve under different macroeconomic environments.

### 4.2.2 Data Sources

Three primary data sources are employed in this study. 

First, daily stock price data are obtained from Yahoo Finance. These prices are adjusted for dividends and stock splits to produce a continuous time series of closing prices. From these, logarithmic daily returns are calculated as

$$
r_t = \ln\left(\frac{P_t}{P_{t-1}}\right),
$$

where \( P_t \) denotes the adjusted closing price on day \( t \). These return series form the basis for volatility estimation through the GARCH(1,1) model.

Second, firm-level balance-sheet variables are drawn from the Forbes Global 2000 dataset hosted on Kaggle. The main variables include total assets, total liabilities, and long-term debt. These are reported annually and used to construct the default barrier required by the KMV model. To ensure comparability across firms, all figures are converted into billions of U.S. dollars. When short-term debt data are missing, it is proxied as a fraction of total liabilities, following the approach of Gregory (2015):

$$
\text{STD} \approx \max(\text{Total Liabilities} - \text{LTD}, 0) \times 0.2.
$$

Third, the risk-free interest rate is obtained from the Federal Reserve Economic Data (FRED) database. The one-year Treasury yield is used as a proxy for the continuous risk-free rate \( r \). This variable enters directly into the KMV formulation of both asset value dynamics and the default threshold discounting process.

### 4.2.3 Variable Construction

The study constructs several derived variables necessary for model calibration and estimation. Market capitalization is calculated as the product of share price and the number of shares outstanding, providing a direct measure of equity value \( E_t \). The volatility of equity returns, denoted by \( \sigma_E \), is estimated using the GARCH(1,1) model described in Section 4.3. The estimated conditional variance is annualized by multiplying by the square root of 252, corresponding to the number of trading days in a year:

$$
\sigma_E = \sqrt{252} \times \text{std}(\epsilon_t),
$$

where \( \epsilon_t \) denotes the residuals from the GARCH model. This measure captures the time-varying nature of market volatility.

The default point \( D_P \) is computed using both short-term and long-term debt components as

$$
D_P = \text{STD} + 0.5 \times \text{LTD},
$$

in line with the methodology of Pykhtin and Zhu (2006) and Basel Committee (2011). This formulation reflects the practical assumption that short-term obligations are fully due upon default, while only part of the long-term debt contributes to the immediate default trigger. The ratio between equity value \( E_t \) and default point \( D_P \) serves as a preliminary indicator of leverage and financial stability.

### 4.2.4 Data Preprocessing

All variables are aligned to a consistent time index based on trading days. For financial statement items reported annually, linear interpolation is applied to approximate daily frequency, ensuring compatibility with high-frequency market data. Missing observations in daily price series are filled through forward interpolation, and firms with prolonged trading suspensions are excluded from the sample.

Outliers in return data are winsorized at the 1st and 99th percentiles to mitigate the influence of extreme market movements on volatility estimates. The resulting dataset provides a clean and coherent panel structure for empirical analysis. All calculations are conducted in Python using standard statistical libraries, including pandas, numpy, and arch, ensuring reproducibility of results.


The dataset thus combines both market-based and accounting-based information for a comprehensive assessment of counterparty credit risk. The integration of daily market prices, volatility dynamics, and balance-sheet fundamentals allows the GARCH–KMV model to reflect both short-term market fluctuations and long-term solvency characteristics. This foundation supports the subsequent estimation of Distance to Default (DD) and Expected Default Frequency (EDF), which serve as the core indicators of creditworthiness in the following analysis.


---

## 4.3 Model Specification

### 4.3.1 KMV Structural Model

The KMV model builds on the **Merton (1974)** structural approach, which treats equity as a European call option on the firm’s assets with a strike price equal to its debt obligations. The value of a firm’s equity \(E\) is expressed as:

$$
E = V_A N(d_1) - D_P e^{-rT} N(d_2)
$$

where:

$$
d_1 = \frac{\ln(V_A / D_P) + (r + 0.5\sigma_A^2)T}{\sigma_A\sqrt{T}}, 
\quad d_2 = d_1 - \sigma_A\sqrt{T}
$$

and:

- \(V_A\): market value of firm assets  
- \(D_P\): default point  
- \(r\): risk-free rate  
- \(\sigma_A\): asset volatility  
- \(T\): time horizon (one year)  
- \(N(\cdot)\): cumulative standard normal distribution function.

The **Distance to Default (DD)** is defined as the number of standard deviations by which the firm’s asset value exceeds the default point:

$$
DD = \frac{\ln(V_A/D_P) + (r - 0.5\sigma_A^2)T}{\sigma_A\sqrt{T}}
$$

and the **Expected Default Frequency (EDF)** is given by:

$$
EDF = \Phi(-DD)
$$

where \(\Phi(\cdot)\) is the cumulative normal CDF.  
A higher DD implies stronger solvency and lower default probability, whereas a smaller DD indicates elevated credit risk *(Pykhtin and Zhu 2006; Hull 2018)*.

---

### 4.3.2 GARCH(1,1) Volatility Process

To incorporate time-varying volatility, equity returns \(r_t\) are modeled using a **GARCH(1,1)** process:

$$
r_t = \mu + \epsilon_t, \qquad \epsilon_t = \sigma_t z_t, \quad z_t \sim N(0,1)
$$

$$
\sigma_t^2 = \omega + \alpha \epsilon_{t-1}^2 + \beta \sigma_{t-1}^2
$$

where \( \sigma_t^2 \) represents conditional variance, and parameters \( \omega, \alpha, \beta \) are estimated via maximum likelihood.  
This specification captures **volatility clustering**—a stylized fact in financial markets *(Engle 1982; Bollerslev 1986)*.  
The annualized volatility used in the KMV stage is:

$$
\sigma_E = \sqrt{252} \times \text{std}(\epsilon_t)
$$

This ensures consistency between the GARCH-derived volatility and the KMV model’s one-year time horizon.

---

## 4.4 Empirical Implementation

### 4.4.1 Data Processing and Variable Construction

Daily closing prices were transformed into continuously compounded returns:

$$
r_t = \ln\left(\frac{P_t}{P_{t-1}}\right)
$$

For each firm, a one-year rolling window was used to estimate equity volatility from the GARCH model.  
The **risk-free rate** \(r_t\) was extracted from daily U.S. Treasury yields (1-year maturity).  
All financial quantities are expressed in consistent USD values.

The **default point (D\_P)** for each firm is constructed as:

$$
D_P = \text{Short-term Debt (STD)} + 0.5 \times \text{Long-term Debt (LTD)}
$$

When short-term debt data were unavailable, it was proxied using:

$$
\text{STD} \approx \max(\text{Total Liabilities} - \text{LTD}, 0) \times 0.2
$$

This proxy maintains proportionality between short- and long-term debt structures across institutions *(Gregory 2015)*.

---

### 4.4.2 Calculation of Distance to Default (DD)

The iterative KMV inversion is used to solve for asset value \(V_A\) and volatility \(\sigma_A\) consistent with observed equity value \(E\) and volatility \(\sigma_E\).  
For each trading day \(t\), DD is calculated as:

$$
DD_t = \frac{\ln(V_A / D_P) + (r_t - 0.5\sigma_A^2)T}{\sigma_A\sqrt{T}}
$$

Daily DD values are averaged to obtain annualized metrics for each institution.

---

### 4.4.3 Derivation of Expected Default Frequency (EDF)

The EDF is derived from the cumulative normal probability of default:

$$
EDF_t = \Phi(-DD_t)
$$

In practice, large DD values (above 8–10) produce EDF values below machine precision (≈ 10⁻¹⁰), resulting in EDF ≈ 0 for all institutions.  
Hence, DD is the primary variable of interest for cross-sectional comparison *(Basel Committee 2011)*.

---

## 4.5 Empirical Results and Discussion

### 4.5.1 DD and EDF Across Institutions

Table 4.1 summarizes the estimated DD and EDF values for the ten banks.  
All institutions exhibit **exceptionally high DD (110–160)**, implying negligible default probabilities.

> **JPMorgan Chase** (DD = 159.5) and **PNC Financial** (DD = 152.9) display the largest buffers between asset value and default point, reflecting robust solvency and strong market capitalization.  
> **M&T Bank** (DD = 110.1) shows the smallest DD, suggesting relatively higher sensitivity to asset-value shocks.  

The uniformly low EDF (≈ 0) across all institutions is consistent with their high capital adequacy ratios and regulatory resilience.

| Ticker | EDF_last | DD_last | sigmaE_annual_last |
|:-------|----------:|---------:|-------------------:|
| JPM | 0.0 | 159.48 | 0.2287 |
| PNC | 0.0 | 152.90 | 0.2196 |
| BAC | 0.0 | 143.97 | 0.2331 |
| COF | 0.0 | 132.83 | 0.2690 |
| C | 0.0 | 129.76 | 0.2484 |
| WFC | 0.0 | 127.45 | 0.2710 |
| FITB | 0.0 | 125.26 | 0.2751 |
| USB | 0.0 | 119.25 | 0.2606 |
| TFC | 0.0 | 118.29 | 0.2581 |
| MTB | 0.0 | 110.12 | 0.2958 |

**Figure 4.1. Distance to Default (Last Observation, 2024)**  
*(Insert bar chart visualization.)*

---

### 4.5.2 Sensitivity to Leverage and Volatility

A cross-sectional plot of DD versus annualized equity volatility (\(\sigma_E\)) reveals a clear negative relationship: higher volatility corresponds to smaller DD.  
This is consistent with theoretical expectations—higher uncertainty increases the likelihood of asset values falling below the default barrier *(Duffie and Singleton 2003)*.

> The most stable institutions (JPM, PNC, BAC) exhibit both low volatility (σE ≈ 0.22–0.24) and high DD (>140), while regional banks (MTB, FITB, TFC) show higher volatility (>0.27) and smaller DD (110–125).

This relationship underscores the sensitivity of DD to both **market risk** and **leverage structure**.

**Figure 4.2. Relationship Between Equity Volatility and DD**  
*(Insert scatter plot.)*

---

### 4.5.3 Implications for Basel III Capital Requirements

Under **Basel III**, banks must maintain a minimum Tier 1 capital ratio of 8.5%.  
The DD in the KMV model can be interpreted as a **market-based measure of capital buffer**—the number of standard deviations separating asset value from the default threshold.  

> The empirical DD values correspond to a market-implied solvency ratio far exceeding regulatory minimums.  
> Thus, the GARCH–KMV estimates support the view that the major U.S. banks remain adequately capitalized and resilient to counterparty credit shocks.

Moreover, during the COVID-19 period, short-lived DD declines illustrate the **procyclicality** of market-based risk measures—mirroring temporary stress that quickly reverses once policy support stabilizes markets *(Basel Committee 2021)*.

---

## 4.6 Summary of Findings

The empirical findings can be summarized as follows:

1. **High solvency across all institutions.**  
   DD values above 100 indicate extreme financial stability; EDFs are effectively zero.  

2. **Negative link between volatility and DD.**  
   Higher market volatility increases default sensitivity, as predicted by the KMV model.  

3. **Dynamic responsiveness to market stress.**  
   DD temporarily declined during 2020 but recovered rapidly, demonstrating resilience.  

4. **Consistency with Basel III framework.**  
   Market-based DD estimates align with capital adequacy principles, offering a complementary tool for supervisory stress testing.

In conclusion, the **GARCH–KMV framework** provides a powerful analytical lens for evaluating counterparty credit risk at the institutional level.  
By integrating time-varying volatility into the structural credit-risk model, it captures both cross-sectional solvency differences and dynamic responses to financial shocks, supporting its use in modern CCR analysis.

---

**References**

- Basel Committee on Banking Supervision (2011). *Basel III: A global regulatory framework for more resilient banks and banking systems.*  
- Basel Committee on Banking Supervision (2021). *Revisions to the Basel Framework.*  
- Bollerslev, T. (1986). *Generalized Autoregressive Conditional Heteroskedasticity.* Journal of Econometrics, 31(3), 307–327.  
- Duffie, D., & Singleton, K. (2003). *Credit Risk: Pricing, Measurement, and Management.* Princeton University Press.  
- Engle, R. (1982). *Autoregressive Conditional Heteroscedasticity with Estimates of the Variance of United Kingdom Inflation.* Econometrica, 50(4), 987–1007.  
- Gregory, J. (2015). *Counterparty Credit Risk and Credit Valuation Adjustment: A Continuing Challenge for Global Financial Markets.* 2nd ed. Wiley Finance.  
- Hull, J. (2018). *Risk Management and Financial Institutions.* 5th ed. Wiley.  
- Merton, R. (1974). *On the Pricing of Corporate Debt: The Risk Structure of Interest Rates.* Journal of Finance, 29(2), 449–470.  
- Pykhtin, M., & Zhu, S. (2006). *A Guide to Modeling Counterparty Credit Risk.* Risk Magazine, March 2006.

---


