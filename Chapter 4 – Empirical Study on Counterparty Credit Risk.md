# Chapter 4. Empirical Analysis of Counterparty Credit Risk

## 4.1 Overview

## 4.1 Overview

We has applied the GARCH–KMV framework to quantify counterparty credit risk (CCR) among major U.S. banking institutions over the 2018–2024 period. The methodology integrates market-derived equity volatility with balance sheet fundamentals to construct firm-specific measures of Distance to Default (DD) and Expected Default Frequency (EDF).

The empirical investigation pursues three primary objectives. First, it operationalizes the KMV structural credit risk model while incorporating GARCH-based conditional volatility estimates to account for time-varying market risk dynamics. Second, it derives institutional default probabilities through the estimation of each bank's distance to the default threshold. Third, it examines the implications of these risk measures for regulatory capital requirements under the Basel III accords.

---

## 4.2 Data Description

The empirical analysis draws upon daily equity market data and quarterly balance sheet information for a sample of systemically important U.S. banking institutions observed between 2018 and 2024. The sample is intentionally restricted to major banks to ensure that the estimated risk metrics capture sector-wide dynamics rather than firm-specific idiosyncrasies that may not be representative of systemic counterparty credit risk.

### 4.2.1 Sample Selection

The analysis covers ten publicly listed U.S. banks: JPMorgan Chase (JPM), Bank of America (BAC), Citigroup (C), Capital One (COF), PNC Financial (PNC), Wells Fargo (WFC), M&T Bank (MTB), Fifth Third Bank (FITB), Truist Financial (TFC), and U.S. Bancorp (USB). These institutions are selected on the basis of market capitalization, data availability, and their importance within the interbank and derivatives markets. Together, they represent a significant portion of total U.S. banking assets and form an appropriate sample for studying counterparty credit risk under the Basel III framework.

The observation period spans from January 2018 to December 2024. This period is chosen to include both normal and stressed financial conditions, most notably the COVID-19-induced market disruptions in 2020, followed by subsequent recovery phases. The seven-year horizon allows for a comprehensive examination of how solvency indicators evolve under different macroeconomic environments.

### 4.2.2 Data Sources

Three primary data sources are employed in this study. 

First, daily stock price data are obtained from Yahoo Finance. These prices are adjusted for dividends and stock splits to produce a continuous time series of closing prices. From these, logarithmic daily returns are calculated as

$$
r_t = \ln\left(\frac{P_t}{P_{t-1}}\right),
$$

where \( P_t \) denotes the adjusted closing price on day \( t \). These return series form the basis for volatility estimation through the GARCH(1,1) model.

Second, firm-level balance-sheet variables are drawn from the Forbes Global 2000 dataset. The main variables include total assets, total liabilities, and long-term debt. These are reported annually and used to construct the default barrier required by the KMV model. To ensure comparability across firms, all figures are converted into billions of U.S. dollars. When short-term debt data are missing, it is proxied as a fraction of total liabilities, following the approach of Gregory (2015):

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

This section presents the theoretical foundation of the empirical model used to quantify counterparty credit risk. The model integrates the structural credit-risk framework proposed by Merton (1974) with a GARCH(1,1) volatility process to account for time-varying risk dynamics. The combined structure enables the simultaneous analysis of firm-level solvency and market-driven volatility.

### 4.3.1 The KMV Structural Model

The structural model of credit risk originates from Merton (1974), who models a firm’s equity as a European call option written on its total asset value. Under this framework, the firm is considered to default when the value of its assets falls below a critical threshold, known as the default point. The firm’s asset value \( V_A \) is assumed to follow a geometric Brownian motion of the form

$$
dV_A = \mu_A V_A \, dt + \sigma_A V_A \, dW_t,
$$

where \( \mu_A \) denotes the expected rate of return on assets, \( \sigma_A \) represents the volatility of asset returns, and \( dW_t \) is a standard Wiener process. At maturity \( T \), the firm’s debt obligation is denoted by \( D_P \), representing the total value of debt due. Default occurs when \( V_A(T) < D_P \).

Within this structure, the market value of equity \( E \) is given by the Black–Scholes option pricing formula:

$$
E = V_A N(d_1) - D_P e^{-rT} N(d_2),
$$

where

$$
d_1 = \frac{\ln(V_A / D_P) + (r + 0.5 \sigma_A^2) T}{\sigma_A \sqrt{T}}, 
\quad d_2 = d_1 - \sigma_A \sqrt{T}.
$$

Here, \( r \) represents the risk-free interest rate, \( N(\cdot) \) is the cumulative standard normal distribution, and \( T \) is the time horizon. Equity volatility \( \sigma_E \) is linked to asset volatility \( \sigma_A \) through the partial derivative of equity value with respect to asset value:

$$
\sigma_E = \frac{V_A N(d_1)}{E} \, \sigma_A.
$$

The model can be inverted numerically to solve for \( V_A \) and \( \sigma_A \) given observed market equity \( E \), its volatility \( \sigma_E \), and debt value \( D_P \). This inversion allows the estimation of the unobservable asset-side variables required for default analysis.

The probability of default is represented by the Expected Default Frequency (EDF), which is obtained as the probability that the firm’s asset value will fall below its default point within horizon \( T \):

$$
EDF = \Phi(-DD),
$$

where the Distance to Default (DD) is defined as

$$
DD = \frac{\ln(V_A / D_P) + (r - 0.5 \sigma_A^2) T}{\sigma_A \sqrt{T}}.
$$

The DD therefore measures the number of standard deviations by which the current asset value exceeds the default point. A larger DD implies greater solvency, whereas a smaller DD indicates higher credit risk. According to empirical literature, DD provides a more stable and interpretable measure of credit quality than EDF, particularly for large financial institutions with low observed default frequencies (Pykhtin and Zhu 2006; Hull 2018).

### 4.3.2 The GARCH(1,1) Volatility Process

A key limitation of the traditional KMV model lies in its assumption of constant asset volatility. Empirical evidence shows that financial markets exhibit volatility clustering and persistence, especially during times of crisis. To address this, the present study employs the Generalized Autoregressive Conditional Heteroskedasticity (GARCH) model introduced by Engle (1982) and extended by Bollerslev (1986). The GARCH(1,1) process defines the conditional variance of returns as follows:

$$
r_t = \mu + \epsilon_t, \qquad \epsilon_t = \sigma_t z_t, \quad z_t \sim N(0,1),
$$

$$
\sigma_t^2 = \omega + \alpha \epsilon_{t-1}^2 + \beta \sigma_{t-1}^2,
$$

where \( \omega > 0 \), \( \alpha, \beta \geq 0 \), and \( \alpha + \beta < 1 \). The parameters \( \alpha \) and \( \beta \) capture the persistence of volatility shocks. The model implies that large innovations in returns (high \( \epsilon_t^2 \)) increase future volatility, while previous volatility (\( \sigma_{t-1}^2 \)) decays gradually over time.

The conditional variance \( \sigma_t^2 \) provides a time-varying measure of market uncertainty. Annualized equity volatility \( \sigma_E \) is computed from the GARCH process as

$$
\sigma_E = \sqrt{252} \times \text{std}(\epsilon_t),
$$

reflecting the annualized standard deviation of daily residuals. This dynamic volatility estimate replaces the constant volatility assumption of the standard KMV model, ensuring that the resulting DD and EDF reflect current market conditions.

### 4.3.3 Integration of GARCH and KMV Models

The integration of the GARCH and KMV frameworks allows the model to incorporate both firm fundamentals and market-driven dynamics. In this combined structure, the GARCH model captures short-term fluctuations in equity volatility, while the KMV model translates this information into credit-risk metrics such as DD. The iterative estimation proceeds as follows:

1. Estimate daily equity volatility \( \sigma_E \) from the GARCH(1,1) model.  
2. Use market capitalization \( E_t \), equity volatility \( \sigma_E \), risk-free rate \( r_t \), and the default point \( D_P \) to solve the KMV system for \( V_A \) and \( \sigma_A \).  
3. Compute DD using the standard KMV formulations.  

This approach produces a sequence of daily DD estimates that capture both firm-specific risk and systemic market volatility. The dynamic nature of this model makes it suitable for analyzing time-varying solvency and for stress-testing purposes in counterparty credit-risk management. Moreover, it enables an empirical comparison of market-implied solvency measures with regulatory capital standards such as those defined under Basel III (Basel Committee 2011).

The model specification unifies structural and econometric methodologies. The KMV model provides the theoretical foundation linking firm assets and liabilities, while the GARCH process supplies the dynamic component necessary to reflect evolving market volatility. Together, they form a coherent analytical framework for the empirical measurement of counterparty credit risk.

---

## 4.4 Empirical Implementation

This section explains how the GARCH–KMV model described in the previous section is implemented empirically. The implementation involves transforming the theoretical model into estimable quantities using the market and accounting data introduced in Section 4.2. The process consists of four main stages: data preparation, parameter estimation, default point construction, and computation of distance to default (DD) and expected default frequency (EDF).

### 4.4.1 Data Processing and Variable Construction

The empirical analysis uses daily closing prices for each bank from January 2018 to December 2024. The continuously compounded daily returns are calculated according to

$$
r_t = \ln\left(\frac{P_t}{P_{t-1}}\right),
$$

where \( P_t \) denotes the adjusted closing price on day \( t \). Outliers in return series are winsorized at the 1st and 99th percentiles to reduce the influence of extreme market movements. The cleaned return series is then used to estimate conditional volatility through the GARCH(1,1) model defined in Section 4.3.2. The conditional variance \( \sigma_t^2 \) obtained from the GARCH process represents daily equity volatility and is subsequently annualized as

$$
\sigma_E = \sqrt{252} \times \text{std}(\epsilon_t),
$$

where \( \epsilon_t \) are residuals from the conditional mean equation.

Firm-level accounting variables, including total liabilities and long-term debt, are aligned with the same observation period. As balance-sheet data are reported annually, linear interpolation is applied to generate daily frequency series, ensuring consistency between market and accounting data. All variables are expressed in U.S. dollars and converted to logarithmic form where appropriate to mitigate heteroskedasticity.

### 4.4.2 Estimation of Model Parameters

The GARCH(1,1) parameters \( \omega \), \( \alpha \), and \( \beta \) are estimated using maximum likelihood. The model is fitted to each firm’s daily return series, and diagnostic tests are performed to confirm the absence of serial correlation in standardized residuals. The estimated conditional volatility \( \sigma_t \) provides a time-varying measure of market uncertainty and serves as input for the KMV model.

The risk-free rate \( r_t \) is taken as the continuously compounded one-year Treasury yield retrieved from the FRED database. Since Treasury yields are reported at daily frequency, no further transformation is required. The time horizon \( T \) is set to one year, consistent with both Basel regulatory convention and the KMV default horizon.

### 4.4.3 Construction of the Default Point

The default point \( D_P \) represents the total debt level that triggers insolvency and is defined as

$$
D_P = \text{STD} + 0.5 \times \text{LTD},
$$

where STD and LTD denote short-term and long-term debt, respectively. This definition follows the recommendation of Pykhtin and Zhu (2006) and reflects the assumption that short-term liabilities are immediately due upon default, while long-term obligations contribute partially to the default trigger.

In cases where short-term debt data are missing, a proxy is employed following Gregory (2015):

$$
\text{STD} \approx \max(\text{Total Liabilities} - \text{LTD}, 0) \times 0.2.
$$

This approximation assumes that approximately 20 percent of non-long-term liabilities are short-term in nature. Although simplified, this method maintains a realistic proportion between short-term and long-term debt for large financial institutions. The total default point is recalculated annually for each firm using the most recent financial statements, and the interpolated series is synchronized with the daily market data.

### 4.4.4 Solving for Asset Value and Volatility

For each firm and each trading day, the asset value \( V_A \) and asset volatility \( \sigma_A \) are inferred by solving the following system of equations derived from the KMV model:

$$
E = V_A N(d_1) - D_P e^{-rT} N(d_2),
$$

$$
\sigma_E = \frac{V_A N(d_1)}{E} \sigma_A,
$$

where \( E \) is market capitalization and \( \sigma_E \) is the observed equity volatility obtained from the GARCH(1,1) model. These equations are solved iteratively using a numerical optimization procedure until convergence is achieved. The solutions \( V_A \) and \( \sigma_A \) are then substituted into the KMV expression for distance to default.

### 4.4.5 Computation of Distance to Default and EDF

Once \( V_A \) and \( \sigma_A \) are obtained, the distance to default for each firm on day \( t \) is calculated as

$$
DD_t = \frac{\ln(V_A / D_P) + (r_t - 0.5 \sigma_A^2) T}{\sigma_A \sqrt{T}}.
$$

The DD measures the number of standard deviations by which a firm’s asset value exceeds its default barrier. A higher DD implies greater solvency and lower default probability. The corresponding expected default frequency is calculated as

$$
EDF_t = \Phi(-DD_t),
$$

where \( \Phi(\cdot) \) denotes the cumulative distribution function of the standard normal distribution. For large, well-capitalized financial institutions, resulting in EDF values close to zero due to numerical precision limits. Consequently, the analysis primarily focuses on DD as the principal indicator of credit quality and solvency.


---

## 4.5 Empirical Results and Discussion

The analysis focuses on the estimation of the distance to default (DD) for ten major U.S. banks and interprets the results in terms of solvency, volatility sensitivity, and capital adequacy. The discussion is organized into three parts. The first part describes the general level and ranking of DD across institutions. The second examines the relationship between solvency, leverage, and market volatility. The third discusses the implications of these results for the Basel III regulatory framework.

### 4.5.1 Distance to Default Across Institutions

<img width="1416" height="214" alt="1" src="https://github.com/user-attachments/assets/d2a835da-a39e-48d4-9dad-955d757738e1" />  
<img width="805" height="455" alt="DD_Ranking" src="https://github.com/user-attachments/assets/bfa3d60f-9c33-4319-84eb-b83239063aa1" /> 

Figures presents the cross-sectional distribution of distance to default (DD) across the ten sample institutions as of the final observation date, alongside the relationship between equity volatility and solvency margins. The upper panel reveals considerable dispersion in DD values, ranging from approximately 110 for M&T Bank to 160 for JPMorgan Chase. This 45% spread, while occurring at uniformly high absolute levels, reflects meaningful differences in market-perceived creditworthiness among institutions.
JPMorgan Chase and PNC Financial emerge as the most solvent institutions by this metric, consistent with their status as diversified, systemically important banks with substantial capital buffers and stable earnings profiles. Bank of America and Capital One Financial occupy the upper-middle tier, while regional banks such as Truist Financial, U.S. Bank, and M&T Bank cluster toward the lower end of the distribution. Notably, even the institution with the lowest DD—M&T Bank at 110—maintains a solvency margin that implies negligible default probability under any realistic scenario.
The lower panel illustrates the inverse relationship between equity volatility (σ_E) and distance to default, a core prediction of the structural credit risk framework. Institutions with lower volatility—JPM (σ_E ≈ 0.23) and PNC (σ_E ≈ 0.22)—exhibit substantially higher DD values, reflecting both greater stability in market valuations and larger capital cushions. Conversely, M&T Bank, with the highest volatility at approximately 0.295, displays the lowest DD in the sample. This negative correlation (ρ ≈ -0.85) confirms that solvency margins compress as asset value uncertainty increases, even when absolute leverage ratios remain similar across institutions.
The observed pattern also reveals a nonlinear effect: the marginal impact of volatility on DD appears more pronounced at lower volatility levels. For instance, the gap between JPM and BAC (Δσ_E ≈ 0.01) corresponds to a DD difference of roughly 15 points, whereas the comparable volatility difference between USB and MTB yields a smaller DD spread. This suggests diminishing sensitivity at higher volatility levels, consistent with the convexity inherent in the Merton model's asset-value dynamics.
From a risk management perspective, these results underscore two key insights. First, while all institutions maintain comfortable solvency margins, the cross-sectional ranking provides a meaningful hierarchy for counterparty risk assessment. JPM and PNC would represent lower-risk counterparties relative to regional banks, all else equal. Second, the volatility-DD relationship highlights the importance of incorporating time-varying risk dynamics: institutions with historically stable equity volatility may experience sharper deteriorations in creditworthiness during stress episodes when volatility spikes unexpectedly.

### 4.5.2 Sensitivity to Leverage and Volatility

A central feature of the GARCH–KMV framework is its ability to link solvency measures to both balance-sheet fundamentals and market-based volatility. To examine this relationship, the annualized equity volatility estimated from the GARCH(1,1) process is compared with the DD obtained from the KMV model. The analysis reveals a clear inverse relationship: institutions exhibiting higher equity volatility tend to have smaller distances to default. 

This negative association reflects the theoretical prediction that increased market uncertainty compresses solvency margins by raising the probability that asset values could approach the default barrier. For instance, large banks such as JPMorgan Chase and PNC Financial, which display relatively low volatility (around 0.22), correspondingly exhibit high DD values above 150. In contrast, institutions such as M&T Bank and Fifth Third Bank, with volatilities near 0.28–0.30, show DD values closer to 110–120. 

This relationship underscores the importance of market volatility as a driver of short-term credit risk dynamics. The GARCH(1,1) model captures this effect through its persistence parameter, which allows shocks in volatility to influence solvency over time. A temporary increase in volatility, such as that observed during the COVID-19 market shock in early 2020, leads to a mechanical decline in DD, even if underlying fundamentals remain unchanged. This dynamic adjustment reflects the model’s sensitivity to market stress and supports its interpretation as a forward-looking risk measure.

Leverage also plays a crucial role in determining DD. Institutions with higher leverage, as reflected by the ratio of liabilities to assets, show systematically lower DD values. This pattern is intuitive: as leverage increases, the distance between assets and the default threshold narrows, thereby increasing default sensitivity. The results therefore confirm that both market-based volatility and accounting-based leverage jointly shape solvency outcomes. The consistency of this relationship across institutions supports the validity of the GARCH–KMV model for quantifying counterparty credit risk in a multi-bank setting.

### 4.5.3 Implications for Basel III Capital Adequacy

The empirical findings have direct relevance for assessing capital adequacy under the Basel III framework. Within the KMV model, the distance to default can be interpreted as a market-based measure of the capital buffer separating a firm’s asset value from its default barrier. A higher DD corresponds to a greater surplus of assets over liabilities, which can be viewed as a market-implied counterpart to the regulatory Tier 1 capital ratio. 

The results indicate that all ten institutions maintain DD values well above levels that would correspond to regulatory solvency thresholds. Large universal banks such as JPMorgan Chase, PNC Financial, and Bank of America exhibit the strongest buffers, consistent with their roles as globally systemically important banks (G-SIBs). Their high DD levels imply that the market perceives their solvency as robust, even during volatile periods. Meanwhile, smaller institutions with lower DD values still display sufficient buffers to meet or exceed Basel III capital requirements.

An important observation is that DD, as a market-implied metric, reacts continuously to changes in volatility and investor sentiment, whereas regulatory capital ratios are based on periodic financial reports. Thus, the GARCH–KMV framework provides a complementary perspective to regulatory measures by offering a real-time indicator of market confidence in a firm’s solvency. The model’s sensitivity to market dynamics enables early detection of potential risk deterioration before it becomes evident in regulatory filings.

In addition, the comparative stability of DD rankings across institutions suggests that the GARCH–KMV model captures structural differences in risk rather than transitory noise. Institutions with persistently higher DD values also tend to maintain higher capitalization ratios and more conservative risk management practices. This alignment between model-based solvency measures and regulatory assessments strengthens the case for using DD as a supplementary metric in capital adequacy evaluation and counterparty risk monitoring.

### 4.5.4 Discussion

The empirical results as a whole demonstrate that integrating time-varying volatility through the GARCH(1,1) specification significantly enhances the explanatory power of the structural KMV model. The resulting DD estimates are not static but evolve dynamically with market conditions, reflecting both firm-specific factors and systemic shocks. The model therefore bridges the gap between purely structural models, which rely solely on balance-sheet data, and reduced-form approaches that capture only market-implied risk.

From a practical standpoint, the estimated DD can be interpreted as a market-based solvency buffer that complements regulatory capital measures. For risk managers, tracking the evolution of DD provides a continuous assessment of counterparty creditworthiness and can serve as an early-warning indicator for potential stress. For regulators, incorporating DD-based indicators into supervisory monitoring frameworks could improve the timeliness and sensitivity of systemic risk assessment. 


---

## 4.6 Summary of Findings

The application of the GARCH–KMV framework to ten major U.S. banking institutions over 2018–2024 yields several noteworthy findings regarding counterparty credit risk dynamics in the post-crisis regulatory environment.
The estimated distance to default (DD) values, ranging between 110 and 160 across all sample institutions, indicate substantial solvency margins throughout the observation period. These magnitudes correspond to negligible expected default frequencies (EDF), effectively near zero for all banks. Such outcomes are consistent with the high capitalization standards imposed under Basel III and reflect the relatively stable macrofinancial conditions that have characterized the U.S. banking sector since the 2008 financial crisis.

Cross-sectional variation in DD values reveals meaningful differences in institutional risk profiles. Systemically important banks such as JPMorgan Chase and PNC Financial consistently maintain the highest solvency margins, reflecting robust capital buffers and diversified risk exposures. Regional institutions including M&T Bank and Truist Financial exhibit modestly lower DD estimates, suggesting greater sensitivity to market volatility. Nonetheless, all institutions remain well above critical default thresholds throughout the sample period.

The role of volatility and leverage in determining solvency is confirmed through the GARCH(1,1) specification. Higher conditional volatility compresses DD by amplifying uncertainty surrounding asset valuations, while elevated leverage ratios mechanically reduce the distance between asset and liability values. The incorporation of time-varying volatility thus captures risk dynamics that would remain undetected under constant-volatility assumptions, particularly during periods of market stress such as the COVID-19 pandemic in 2020. The temporary decline in DD during this episode, followed by rapid recovery, demonstrates the model's responsiveness to macroeconomic shocks.
From a regulatory perspective, the market-implied solvency measures align closely with Basel III capital requirements. The observed DD values correspond to capital buffers substantially exceeding the minimum Tier 1 ratio of 8.5 percent, though the market-based approach offers a forward-looking and continuously updated assessment that complements static regulatory metrics. This dual perspective proves valuable for real-time counterparty risk monitoring and provides a bridge between accounting-based capital measures and market-implied risk indicators.

The empirical analysis demonstrates that integrating GARCH-based volatility into the structural credit risk framework yields coherent and empirically robust assessments of banking sector solvency. These findings not only validate the theoretical foundations of the model but also establish its practical utility for financial stability surveillance and capital adequacy evaluation. The synthesis of these results with broader theoretical and policy considerations will be addressed in the concluding chapter.


---




