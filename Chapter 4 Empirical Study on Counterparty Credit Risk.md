# Chapter 4 Empirical Study on Counterparty Credit Risk

## 4.1 Selection of Variables

### 4.1.1 Sample Data

To verify the applicability of the KMV model in the measurement of counterparty credit risk, this study selects listed financial institutions as research samples. The data are obtained from public financial statements and market price databases. The observation period covers five consecutive fiscal years to ensure that both stable and volatile market phases are represented.

The key variables include total assets, total liabilities, equity market value, debt maturity, and daily stock-price volatility. All data are processed in logarithmic form to reduce heteroskedasticity and enhance the stability of model estimation.

### 4.1.2 Credit Risk Measurement

Credit-risk exposure is defined as the potential loss that a financial institution may suffer due to counterparty default. The exposure of each counterparty is estimated using the expected positive exposure (EPE) computed under the KMV model. The general form is expressed as:

$$
EPE = \frac{1}{T}\int_{0}^{T} E[\max(V_t,0)]\,dt
$$

where \(V_t\) is the simulated market value of the counterparty position at time \(t\), and \(T\) represents the contract maturity.

The probability of default (PD) is obtained from the expected default frequency (EDF) estimated in the KMV framework. The counterparty exposure at default (EAD) is then calculated as:

$$
EAD = EPE \times (1 + \alpha)
$$

where \(\alpha\) is a calibration factor reflecting potential future exposure. This approach allows dynamic evaluation of risk sensitivity to market changes (Pykhtin and Zhu 2006).

### 4.1.3 Application of Control Variables

To control for heterogeneity across counterparties, this study introduces firm-specific variables such as leverage ratio, asset turnover, and interest coverage. Market-level controls include the risk-free rate and the volatility index (VIX). These variables are included to isolate the marginal effect of credit-risk factors on counterparty exposure.

---

## 4.2 Model Parameter Settings

### 4.2.1 Debt Value and Maturity

The default point \(D\) is estimated as the sum of short-term liabilities and one-half of long-term liabilities (Duffie 2003). Debt maturity is measured as the weighted average of short- and long-term components. The risk-free rate \(r\) is proxied by the yield of government bonds with equivalent maturity.

### 4.2.2 Equity Volatility

Equity volatility \(\sigma_E\) is computed using a rolling-window method based on daily stock returns. Asset volatility \(\sigma_A\) is obtained through iterative estimation consistent with the Black–Scholes relationship between equity and asset values (Brigo and Capponi 2010):

$$
\sigma_E = \frac{V_A}{E} N(d_1)\sigma_A
$$

where \(V_A\) is the asset value, \(E\) the market capitalization, and \(N(d_1)\) the cumulative normal distribution term from the Black–Scholes model.

---

## 4.3 Empirical Results Analysis

### 4.3.1 Verification Results

Based on the empirical data, the KMV model demonstrates consistent estimation of expected default frequency (EDF) across counterparties. Firms with higher leverage and volatility show higher EDF values, consistent with theoretical expectations. The correlation between estimated EDF and observed credit-spreads data indicates satisfactory predictive ability (Lu and Juan 2011).

### 4.3.2 Counterparty Credit-Risk Exposure

The exposure profile generated from simulated asset paths reveals that uncollateralized positions show higher expected exposure than collateralized ones. The time evolution of \(EE_t\) increases with market volatility but declines as collateralization improves. This finding supports the view that margin requirements effectively reduce credit exposure (Gibson 2005).

### 4.3.3 Risk-Weighted Assets of Counterparty Credit Risk

The risk-weighted asset (RWA) corresponding to counterparty exposures is calculated according to Basel III rules (Basel Committee on Banking Supervision 2011):

$$
RWA_{CCR} = 12.5 \times K_{CCR}
$$

where \(K_{CCR}\) is the capital requirement derived from expected exposure and probability of default. The results show that high-volatility institutions require a larger capital buffer, demonstrating that the KMV-based estimates align with regulatory capital sensitivity.

### 4.3.4 Application of Risk-Neutral Measure

To further evaluate pricing consistency, risk-neutral default probabilities are obtained by transforming the real-world probability \(P\) into a risk-neutral measure \(Q\). Under \(Q\), the expected asset value at time \(T\) is given by:

$$
E^{Q}[V_T] = V_0 e^{(r - 0.5\sigma_A^2)T}
$$

The EDF derived under \(Q\) provides an alternative estimate of credit spreads that can be compared with market-implied default probabilities. The empirical analysis confirms that the KMV model captures both physical and risk-neutral default behavior with acceptable accuracy.

---

<img width="469" height="308" alt="CCR" src="https://github.com/user-attachments/assets/f59be058-79b8-49b5-8137-b9f262772dfc" />
