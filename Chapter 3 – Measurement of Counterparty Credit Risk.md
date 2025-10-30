# Chapter 3 Measurement of Counterparty Credit Risk

## 3.1 Basic Overview of Counterparty Credit Risk

Counterparty credit risk (CCR) refers to the potential loss a financial institution faces when a counterparty in a derivatives or securities-financing transaction defaults before the final settlement of cash flows. Unlike traditional loan credit risk, CCR depends on the market value of the underlying transaction, which can fluctuate over time and may even become negative.

The emergence of CCR is mainly related to the expansion of derivative products. Before the 2008 global financial crisis, banks and investment institutions relied heavily on complex instruments such as credit default swaps (CDS) and collateralized debt obligations (CDOs). When systemic risk intensified, these exposures caused large-scale contagion effects in financial markets (Duffie 2003). Therefore, the accurate measurement of CCR has become a key component of risk management and capital regulation (Basel Committee on Banking Supervision 2006).

## 3.1.1 Evolution of Measurement Models

Since the establishment of the Basel I Accord in 1988, credit risk valuation models represented by the current exposure method have been officially applied to real-world financial transactions. These models were developed to calculate counterparty credit-risk exposures, providing quantitative tools for default-risk measurement. The framework clearly defined valuation standards for interest-rate derivatives, foreign-exchange contracts, and other off-balance-sheet products.  

In the valuation of counterparty credit risk, key parameters include the cost of contractual exposure and potential future exposure at default. By referring to the exposure-at-default (EAD) calculation formula, and considering option and derivative products as examples, the Basel II framework introduced the Credit Valuation Adjustment (CVA) model to modify credit-risk valuation techniques. This allowed institutions to assess the suitability and accuracy of credit-risk measurement models across different product types, taking into account short-term and long-term valuation volatility.

Combining both internal and non-internal model approaches, Basel II extended the current exposure method to incorporate netting and collateral agreements, refining the measurement of net exposures and expected exposure at default. These innovations strengthened the calculation of potential default losses and provided a more realistic basis for assessing counterparty credit risk.  

Under the Basel Committee’s supervisory guidance, transaction-level counterparty credit-risk valuation is now required to integrate multiple risk factors, including collateral, guarantees, and off-balance-sheet cost elements. Together with macroeconomic conditions, these factors form a unified system for credit-risk evaluation that specifies roles for risk managers, auditors, and capital supervisors.  

This integrated framework allows for clearer identification of exposure sources, management responsibilities, and quantitative assessment mechanisms. It also helps establish comprehensive counterparty credit-risk assessment systems that explicitly distinguish between traded and non-traded exposures. The approach combines theoretical principles of risk avoidance, netting, and collateralisation with empirical transaction data to enhance market sensitivity within the SA-CCR (Standardized Approach for Counterparty Credit Risk) framework introduced under Basel III.

The SA-CCR approach addresses deficiencies in previous exposure-measurement standards by improving consistency between market-pricing theory and regulatory capital requirements. It ensures that the evaluation system for counterparty credit risk is complete, accurate, and adaptable to the evolving complexity of financial markets.

## 3.1.2 Measurement of Credit Risk

At present, the management of counterparty credit risk in trading activities is primarily examined from the perspective of both transaction parties. It mainly includes securities financing transactions and derivative-instrument transactions as the two key components. The measurement of credit risk involves two related dimensions: the quantification of default risk and the adjustment of risk-weighted assets.

In estimating the counterparty’s exposure at default, the exposure amount is calculated using the Exposure at Default (EAD) model for derivative instruments. The formula is expressed as:

$$
EAD = MtM + Add\text{-}on
$$

where \( MtM \) represents the mark-to-market value, and \( Add\text{-}on \) denotes the add-on factor for potential future exposure. These two components together capture both current and future exposure risks.

When assessing counterparty risk under central clearing arrangements, the Basel Committee stipulates that approximately 2% of total counterparty exposure should be risk-weighted to reflect systemic concentration. This forms a unified valuation mechanism that helps analyse the pricing efficiency of credit-risk assets. The relationship between the mark-to-market value and the add-on factor ensures that EAD estimation properly accounts for both market-value fluctuations and potential credit exposures.

In the process of adjusting credit-risk asset valuation, the Credit Valuation Adjustment (CVA) serves as an essential parameter for quantifying credit-risk premiums. The CVA risk-weighted value provides a basis for judgment in evaluating the effectiveness of credit-risk measurement and management. By incorporating CVA into the internal-trading framework for derivatives, institutions can more accurately estimate credit-risk exposure and improve the efficiency of risk-based capital assessment.

Overall, this analytical process strengthens the measurement and control of credit-risk capital, offering quantitative support for effective credit-risk management activities. Figure 3.2 illustrates the general workflow of counterparty credit-risk measurement.


## 3.2 Measurement Models of Counterparty Credit Risk

According to the regulatory framework established by the Basel Committee, exposure at default (EAD) is regarded as a core component of counterparty credit-risk management in financial transactions. The Basel standards define several methodologies for measuring such exposures, including the Current Exposure Method (CEM), the Standardized Method (SM), the Internal Model Method (IMM), and the Non-Internal Model Method (NIMM).  

Each of these approaches provides a structured means of assessing credit exposure arising from derivative contracts, securities financing transactions, and other counterparty-based financial instruments. For over-the-counter (OTC) derivatives in particular, the Basel framework emphasizes the need to accurately estimate potential future exposure (PFE) alongside current exposure.  

These models collectively establish a reasonable and comprehensive structure for credit-risk measurement, ensuring that institutions can evaluate both on-balance-sheet and off-balance-sheet exposures under varying market conditions.


### 3.2.1 Current Exposure Method (CEM)

In the measurement of counterparty credit risk, the current exposure method (CEM) is widely adopted as a standardized approach to estimate potential exposure. According to equation (3.1), the total credit exposure amount (CEA) consists of the current replacement cost (CRC) and an additional add-on component representing potential future exposure (PFE). The specific formula is expressed as follows:

$$
CEA = CRC + Add\text{-}on \quad (3.1)
$$

In this framework, market-based credit-risk valuation tools are used to determine the relative weight of potential future exposure (PFE). As shown in Table 3.1, the add-on factors are determined according to the type of underlying transaction and the remaining maturity. The valuation incorporates the mark-to-market (MtM) principle, which allows institutions to assess net replacement costs and evaluate asset value fluctuations. This ensures that contractual asset valuations reflect both current exposure and the potential future volatility of market prices.

#### Table 3.1. PFE Add-on Factors by Product Type and Maturity

| Remaining Maturity | Interest Rate | Foreign Exchange and Gold | Equity | Precious Metals (excl. Gold) | Others |
|--------------------|---------------|----------------------------|---------|------------------------------|---------|
| Less than 1 year   | 0.0%          | 1.0%                       | 6.0%    | 7.0%                         | 10.0%   |
| 1–5 years          | 0.5%          | 5.0%                       | 8.0%    | 7.0%                         | 12.0%   |
| Over 5 years       | 1.5%          | 7.5%                       | 10.0%   | 8.0%                         | 15.0%   |

Based on the transaction counterparties’ contractual exposure maturities, the CEA is computed as the sum of current and potential future exposures. The nominal value of a transaction is multiplied by the fixed add-on factor to estimate total exposure, which captures the maximum potential loss under extreme market conditions.  

The model also applies a standardized weighting approach for PFE, integrating adjustments between add-on and nominal exposure values. This ensures that the exposure calculation reflects the net replacement cost ratio across product types and maturities. Consequently, the weighting of PFE is determined through data calibration and validated by sensitivity and risk-hedging measures.  

This approach provides a consistent and conservative basis for assessing credit exposure, ensuring that institutions adopt rational and risk-sensitive control mechanisms for counterparty credit-risk management.

### 3.2.2 Internal Model Method (IMM)

In the calculation of exposure at default (EAD) under risk-exposure analysis, the relationship between effective expected positive exposure and total risk exposure can be expressed as:

$$
EAD = \alpha \times Effective\ EPF \quad (3.2)
$$

where \( \alpha \) represents a regulatory multiplier, and \( Effective\ EPF \) denotes the effective expected positive exposure (EEPE), which accounts for market-risk-related factors and expresses the expected value of future exposures over time. This formula indicates that exposure estimation is based on the discounted expectation of risk factors across different periods.

The IMM evaluates expected exposure at various time points \( t_1, t_2, t_3, \ldots \), by defining the time-weighted average of the effective expected exposure. The change between successive time intervals \( \Delta t_k = t_k - t_{k-1} \) is used to calculate future expected exposure. The value of \( \alpha \) typically ranges between 1.2 and 1.4, depending on portfolio characteristics. A higher alpha reflects greater dispersion of exposure within the trading portfolio, higher market-value correlation, and stronger counterparty concentration risk.

By incorporating estimated exposure profiles, the IMM assesses risk across multiple dimensions—interest rates, equities, foreign exchange, commodities, and options—while also considering revaluation risks, yield-curve risks, and benchmark-risk parameters. The IMM compares these risk-value estimates with those defined under the Basel Committee’s standardized framework, allowing financial institutions to manage capital allocation limits, establish warning thresholds, and maintain comprehensive records for compliance and supervision.

Through this mechanism, the IMM enhances the sensitivity of capital adequacy to market and credit risks. It allows for a more accurate quantification of exposure under varying market scenarios and provides early-warning indicators for potential losses.

The IMM framework also accounts for the structural characteristics of each derivative transaction, including the behaviour of risk drivers, margining practices, collateral arrangements, contract maturity, and cash-flow distribution. It further evaluates the interdependence of risk factors and exposure concentrations across counterparties.

To ensure prudence in capital measurement, Basel II imposes stricter requirements on banks that adopt the IMM approach. These include the need for rigorous model validation, comprehensive counterparty credit-risk (CCR) management, and the implementation of stress testing, backtesting, and model-building documentation.  

By fulfilling these requirements, institutions can strengthen the transparency and reliability of their credit-risk models, thereby aligning internal exposure assessment with international regulatory standards.

### 3.2.3 Standardized Method (SM)

Under the Standardized Method (SM) framework, the exposure at default (EAD) formula can be simplified as:

$$
EAD = 1.4 \times \max[(CMV - CMC); (RPT - RPC) \times CCF]
$$

where \( CMV - CMC \) represents the difference between the current market value of the derivative contract and the market value of the collateral, and \( RPT - RPC \) denotes the difference between the replacement cost at transaction settlement and the collateral replacement value at that time. \( CCF \) is the credit conversion factor, which converts nominal exposure into risk-weighted exposure according to the Basel II framework.

Compared with the Current Exposure Method (CEM), the SM provides stronger risk sensitivity. In particular, when a derivative transaction involves collateralization and margin agreements, banks must calculate the headroom after netting on a legal and contractual basis. This allows for more precise measurement of net counterparty credit risk.  

Like CEM, however, SM does not explicitly differentiate whether a transaction is collateralized. Instead, EAD is defined as the larger of the current exposure and the potential future exposure. Both measures represent the maximum exposure level the institution might face, with no double counting. The SM also recognizes that the temporal distribution of exposures may differ depending on product type and contractual maturity.

Under standardized backtesting, the SM is applied as the primary framework for computing net replacement cost and counterparty default exposure. The estimation process defines both current and potential future exposures, thereby reflecting the present market value of assets and the corresponding volatility in collateralized or uncollateralized trades.  

The SM framework assumes that changes in the market value of derivatives and collateral are functionally related, generally within a range of 5%. This ensures valuation consistency between the contract and collateral. Under the Standardized Approach for Counterparty Credit Risk (SA-CCR), exposure analysis for both secured and unsecured derivative transactions is performed according to the following general relationship:

$$
EAD = \alpha \times (RC + PFE) \quad (3.3)
$$

where \( RC \) denotes the replacement cost, \( PFE \) represents the potential future exposure, and \( \alpha \) is the regulatory scaling factor, typically fixed at 1.4. The combined value of \( RC + PFE \) reflects the effective expected positive exposure, which represents the bilateral agreement between counterparties for exposure estimation.

The SM separately considers secured and unsecured transactions. In the case of secured derivatives, independent collateral agreements (ICA) are treated as guarantees that reduce exposure. Financial institutions evaluate collateral performance by considering inflows and outflows under the ICA structure. For unsecured transactions, the replacement cost \( RC \) captures the immediate loss upon counterparty default.  

Here, \( CMV_t \) denotes the current market value of the collateral, and \( h(t) \) represents the haircut applied during each time interval to reflect collateral adjustments (including initial margin, variation margin, and other collateralized components).

Within an unknown future time horizon, the SM defines the potential loss upon counterparty default and the close relationship between market value and exposure at the time of default. For a standardized time interval, the SM models exposure evolution based on both collateralized and uncollateralized conditions. The framework calculates changes in \( RC \) over future periods and expresses exposure dynamics through net present valuation.

This provides a consistent and conservative classification of exposure types, ensuring that counterparty credit-risk measurement aligns with Basel III capital requirements while maintaining comparability across institutions.

## 3.3 Measurement of Central Counterparty (CCP) Credit Risk

Since April 2013, the Basel Committee on Banking Supervision (BCBS) has officially released a series of evaluation reports on counterparty credit risk (CCR). These reports focus on the exposure arising from central counterparties (CCPs), aiming to identify market risks associated with central clearing and to enhance the measurement framework for counterparty credit exposure in over-the-counter (OTC) derivatives markets.  

The introduction of CCP-based exposure assessment was designed to address deficiencies in traditional counterparty risk models, particularly those that did not adequately account for clearing processes. By integrating CCP exposures into the broader analysis of counterparty credit risk, the Basel Committee sought to establish a consistent capital evaluation framework applicable to both qualified and non-qualified CCPs.  

The revised framework takes central clearing as the reference point for assessing credit risk and establishes capital valuation criteria based on CCP exposure. It gradually improves the capital-requirement model to ensure comprehensive and risk-sensitive assessment of counterparty exposures.

---

### 3.3.1 Capital Requirement Model

Based on actual default resources and default-fund contributions, the capital requirement model treats the total default resources—including prefunded default funds, members’ contributions, and the CCP’s own capital—as the basis for exposure estimation. Let \( DF^{pref} \) represent the prefunded default resources contributed by clearing members and the CCP. The overall structure of the capital-requirement model can be expressed as:

$$
DF^{pref} = DF^{pref}_{CM} + DF_{CCP} \quad (3.5)
$$

where \( DF^{pref}_{CM} \) denotes the default fund contribution from clearing members and \( DF_{CCP} \) denotes the CCP’s own prefunded resources.

For each clearing member’s contribution, the model establishes its applicable scope by defining the minimum capital standards in accordance with the CPSS-IOSCO regulatory principles. It quantifies both current exposure risk and potential future exposure, incorporating macroeconomic adjustment factors. The capital calibration constant \( K_{CCP} (NIMM) \) is assigned within a defined range to support standardized estimation of central counterparty credit exposure.

The CCP capital framework relies on stress testing to simulate multiple exposure scenarios, in which clearing members, subsidiaries, or corporate entities serve as credit-risk-bearing units. The model integrates maximum and minimum capital requirements to determine exposure equilibrium across future market conditions.  

In computing member-level capital requirements, the prefunded default contributions are considered the key input. Each member’s exposure is analyzed based on different transaction conditions and clearing statuses. The model applies separate parameters for single-member and multi-member structures to ensure that risk allocation reflects systemic interdependencies.

For an individual clearing member, the prefunded default contribution serves as the unit of analysis. The model applies a weighting factor \( \beta \), which adjusts capital requirements based on the member’s exposure magnitude, liquidity position, and operational resilience.  

By linking prefunded resources, default contributions, and exposure measures, the framework establishes a capital-adequacy standard consistent with CCP credit-risk sensitivities. This ensures that credit exposure under both current and potential default conditions is measured prudently and in alignment with international supervisory requirements.


### 3.3.2 Updated Measurement Model

Equity and bond transactions, as well as exchange-traded and over-the-counter (OTC) derivatives, form the primary business products considered in this model. To enhance risk sensitivity and alignment between exposures and capital requirements, the updated framework specifies the matching degree between risk weights and different types of counterparty exposures. This structure prepares financial institutions for potential defaults within central counterparty (CCP) clearing arrangements.

To prevent the default of clearing members and ensure client-transaction safety, the model sets capital requirements for counterparty credit-risk exposures under qualified CCPs. For a clearing member \( i \), the exposure risk weight is controlled at \( RW = 20\% \), and the capital ratio \( capitalratio = 8\% \). Using the prefunded default resources \( DF^{pref} \) contributed by the CCP and its clearing members, the model provides a standardized benchmark for estimating the credit exposure of clearing members. The capital requirement formula is expressed as:

$$
K_{CCP} = \sum_{CM_i} EAD_i \cdot RW \cdot capitalratio \quad (3.6)
$$

where \( EAD_i \) represents the exposure at default for clearing member \( i \), \( RW \) denotes the risk weight assigned to the exposure, and \( capitalratio \) is the capital adequacy ratio specified by the Basel framework.

In addition, a 2% risk-weight standard is applied for qualified CCPs when calculating the capital charge for counterparty exposure. This constant factor ensures consistency in capital treatment of prefunded default resources and reflects the expected probability of member default. The expected transaction-exposure risk weight is denoted as \( RW_{TE} \), and it adjusts for exposure volatility under the non-internal model method (NIMM). The variable \( cover^* \) serves as a reference parameter (or analytical benchmark) to determine the minimum coverage level during the initial clearing phase.

According to the cooperative framework established by the Basel Committee, the exposure risk weight for default-fund contributions is controlled within 2%, in line with the CCP’s qualification criteria. By ensuring that current market values adequately cover potential exposure levels, the model supports regulatory compliance and strengthens supervisory oversight (see also Section 3.3).

