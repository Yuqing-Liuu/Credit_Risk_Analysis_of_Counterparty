# Chapter 2 Research on Relevant Theories

## 2.1 Credit Risk Management Theory

## 2.1.1 Asset Management Theory

The theory of asset management regards cash, loans, securities, and fixed assets as its main components. It is established based on the investment activities of financial institutions to achieve the objectives of asset allocation and service efficiency. In practical operations, financial institutions determine the maturity structure and composition of assets according to funding constraints and cash-flow safety, striving to optimize both the rationality and efficiency of asset structures. The goal is to achieve coordinated development between liquidity, safety, and profitability so that both lending and investment activities can operate effectively and sustainably.

Within this theoretical framework, asset management theory integrates several branches of traditional commercial banking theory, including the commercial loan theory, the shiftability theory, and the anticipated income theory. These frameworks collectively evolved with the needs of modern financial markets and provide a foundation for ensuring that banks can adapt their asset structures to market cycles and the changing demand for funds in the real economy.

(1) **Commercial Loan Theory**  
This theory emerged under the changing environment of traditional commercial credit, focusing on the self-liquidating nature of short-term business loans and the liquidity of commercial assets. It emphasizes that banks should primarily engage in short-term, self-liquidating commercial lending, ensuring that funds are used within a short period to maintain cash-flow circulation. By doing so, commercial banks can enhance the liquidity of short-term industrial and commercial loans and achieve the goal of promoting smooth monetary circulation in the long term.

(2) **Anticipated Income Theory**  
In the 1930s and 1940s, the anticipated income theory expanded the concept of asset management, promoting diversified lending practices. It emphasized that banks could provide loans based on borrowers’ future income expectations, rather than limiting themselves to traditional trade-related short-term lending. This theory increased the flexibility of bank operations, allowing credit to be extended for broader purposes such as consumption and investment. By linking asset liquidity with borrowers’ income projections, this theory offered banks a framework to assess repayment capacity and to control liquidity risk over different horizons.

In addition, later developments such as the shiftability theory and the excess-reserve supply theory further enriched the understanding of asset management. These approaches highlighted the importance of maintaining transferable, high-quality assets that can be converted into cash through market transactions when liquidity is needed. The theories also emphasized that banks should diversify asset allocation across various categories such as loans, securities, and other earning assets, in order to enhance portfolio stability and meet liquidity demands under fluctuating market conditions.

Modern applications of asset management theory involve the comprehensive use of diversified financial instruments, including securities investments, entrusted loans, and other off-balance-sheet products. Financial institutions now focus on planned asset allocation and dynamic adjustment of investment structures to ensure optimal liquidity, safety, and profitability. This framework also provides the theoretical basis for analyzing credit-risk prevention in securities and interbank transactions, contributing to the development of integrated credit-risk management mechanisms that ensure efficient capital utilization and smooth market operations.


## 2.1.2 Liability Management Theory

Since the late 1950s, Western developed economies entered a phase of post-war reconstruction and recovery. During this period, the demand for funds and credit rose sharply, and with the continuous expansion of corporate sales and production scales, financial institutions sought to maximise profitability by diversifying their sources of funding. This gave rise to the concept of “liability management,” which emphasised the use of multiple channels to attract deposits and other sources of funds to support economic recovery and growth.

The theory of liability management proposes that banks should actively adjust their asset scale and structure based on funding capacity and market conditions. It focuses on the role of liabilities as an essential foundation for asset expansion and credit creation. By managing funding sources more flexibly, financial institutions can support broader credit activities and stimulate economic vitality. In this sense, liability management theory represents a shift from the traditional passive acceptance of deposits to an active approach of funding through various instruments and markets.

Liability management theory is built upon credit-risk awareness. To a certain extent, it also increases organisational exposure to high-yield, high-risk borrowing activities. As the use of leveraged funds expands, higher borrowing costs and elevated lending rates intensify market-financing expenses. Enterprises may face liquidity mismatches and refinancing risks when market interest rates fluctuate sharply. Consequently, liability management plays an auxiliary role in helping firms and banks adjust to evolving credit and funding conditions.

Since the Basel Committee on Banking Supervision issued new credit-risk and counterparty-risk frameworks in 2013, liability management has taken on even greater importance. The updated capital requirements for counterparty exposures highlight the need for financial institutions to align liability structures with risk-based capital adequacy ratios. Under these conditions, the liability management framework serves as a crucial complement to asset management, enhancing the institution’s ability to mitigate unexpected funding shocks and market disruptions.

By integrating the logic of liability management into credit-risk analysis, this study evaluates how banks can use diversified borrowing strategies—such as interbank lending, bond issuance, and repurchase agreements—to optimise liquidity and maintain financial stability. The theoretical core of liability management thus provides a foundation for building hierarchical and systematic liquidity-support mechanisms. In doing so, it contributes to the improvement of comprehensive credit-risk management systems.


## 2.2.1 Theoretical Overview

In 1997, the U.S.-based KMV Corporation proposed the KMV model, which is primarily used to estimate the probability of default for borrowing enterprises. The model suggests that, given a certain level of debt, the magnitude of credit risk is determined by the market value of the debtor’s assets. However, since assets themselves are not directly traded in the market, their market value cannot be observed directly. The KMV model therefore transforms the problem of loan default into one of evaluating a firm’s repayment capability by analysing its asset value from the perspective of corporate borrowers.

At maturity, if the market value of a company’s assets exceeds the book value of its liabilities, the firm’s equity value equals the difference between the two. Conversely, if the asset value falls below the debt value, the firm is unable to repay its obligations and must liquidate its assets, rendering the equity value effectively zero.

The KMV model adopts the Black–Scholes option-pricing framework to measure the market value of a firm’s assets. It treats a company’s equity as a call option on its total assets and derives the asset value and volatility from observed market equity value and volatility. Given the company’s total liabilities, time to maturity, and volatility parameters, the model calculates the firm’s default risk from an option-pricing perspective.

The model further defines a “default point” (also known as the default exercise point), usually set as the sum of all short-term debt and half of long-term debt within one year. Based on this threshold, the distance to default (DD) is determined by comparing the market value of assets with the book value of liabilities. The formula can be written as

$$
DD = \frac{\ln(V_A / D) + (r - 0.5\sigma_A^2)T}{\sigma_A \sqrt{T}}
$$

where \( V_A \) is the market value of assets, \( D \) is the book value of debt, \( \sigma_A \) is the asset volatility, \( T \) is the time horizon, and \( r \) represents the risk-free interest rate.

The expected default frequency (EDF) represents the cumulative probability that the firm’s asset value will fall below the debt value within a specified time frame:

$$
EDF = N(-DD)
$$

where \( N(x) \) denotes the cumulative standard normal distribution.

The KMV model evaluates a borrower’s probability of default as a function of asset value, liability structure, and market volatility. It helps mitigate credit risk in the asset market by quantifying potential loan losses and linking them to the borrower’s capital structure. By incorporating transaction data from counterparty exposures under the Basel framework, the model strictly follows the principle of “if the market value of assets exceeds the market value of liabilities, the firm remains solvent; otherwise, the equity value declines to zero.” This principle allows estimation of the overal

## 2.2.2 Research Method of the KMV Model

Based on counterparty credit-risk data analysis, this section applies the KMV model’s theoretical assumptions and practical feasibility to verify the credit-risk estimation of enterprises. Through a continuous measurement process, it aims to reflect the market value of illiquid production assets with reasonable accuracy.

In the analysis of default-exposure risk, 50% of long-term liabilities and 100% of short-term liabilities are treated as the effective benchmark for total debt value. To reflect variation in debt-value sensitivity, a discount range of 70%–75% is used as the adjustment factor for expected debt valuation. This calibration assists in judging the effective range of enterprise liabilities during credit-risk evaluation.

In adjusting counterparty credit risk, the model considers asset-value volatility and applies the option-pricing equilibrium standard to determine the firm’s equity value \(E\), debt value \(D\), asset market value \(V\), risk-free rate \(r\), and cumulative normal distribution parameter \(N\). The enterprise’s debt value is regarded as the strike price, and the model ensures stable transformation between asset value and volatility. The specific calculation formula is as follows:

$$
E = V N(d_1) - D e^{-rT} N(d_2)
$$

In this equation, the market value of equity \(E\) and its volatility \(\sigma_E\) are determined through option-pricing and illiquid-stock discounting methods. The pricing of non-tradable shares is estimated using the empirical formula:

$$
\text{Non-tradable share price} = \text{Tradable share price} \times 22\%
$$

That is, total equity value = (number of tradable shares × closing price) + (number of non-tradable shares × 22% × closing price). The volatility of assets is then adjusted using the GARCH(1,1) model to complete the firm’s asset-value estimation.

Using asset volatility and market value as representative indicators, the parameters \(d_1\) and \(d_2\) can be expressed as:

$$
d_1 = \frac{\ln(V / D) + (r + 0.5\sigma_A^2)T}{\sigma_A \sqrt{T}}, \quad
d_2 = d_1 - \sigma_A \sqrt{T}
$$

These parameters describe the dynamic model of the firm’s market asset value.  

Assuming that total debt value is represented by \(DPT\), long-term liabilities by \(LD\), and short-term liabilities by \(SD\), the firm’s debt structure can be expressed as:

$$
DPT = LD + SD
$$

By analysing changes in asset value and debt volatility, the firm’s credit-risk equilibrium can be represented by the following formula:

$$
DD = \frac{V - DPT}{V\sigma_A}
$$

This expression defines the distance to default (DD) as the fundamental measurement standard for potential default exposure. It captures how far the firm’s asset value must fall before default occurs.

The expected default frequency (EDF) represents the probability that the market value of a firm’s assets will drop below its total debt value. It is expressed as:

$$
EDF = P(V < DPT) = N\left(\frac{DPT - V}{V\sigma_A}\right) = N(-DD)
$$

In this framework, the firm’s future default risk is determined jointly by asset volatility and market value. By substituting the relevant parameters, the model provides a forward-looking indicator of credit exposure. Combining this with the anticipated default probability, the KMV model yields the firm’s credit-risk efficiency, offering a quantitative reference for empirical evaluation.

Therefore, in this study, the KMV model serves as the foundational framework for assessing counterparty credit risk. By integrating dynamic simulation and parameter calibration, it provides a realistic measurement of firms’ default probabilities, supporting effective risk management and regulatory analysis.

