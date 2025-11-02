# Chapter 4 Empirical Study on Counterparty Credit Risk

Chapter 4. Empirical Analysis of Counterparty Credit Risk
4.1 Overview of the Empirical Framework

This chapter investigates counterparty credit risk for major U.S. banks using a GARCH–KMV framework over 2018–2024. The objectives are: (i) to estimate distance to default (DD) and expected default frequency (EDF), (ii) to examine the relation between market volatility and credit risk, and (iii) to interpret the empirical results in the context of Basel III capital adequacy.

4.2 Data and Model Setup
4.2.1 Sample and Sources

Sample: ten U.S. listed banks (JPM, BAC, C, COF, PNC, WFC, FITB, MTB, TFC, USB).
Sources: daily stock prices (Yahoo Finance); balance-sheet items (Forbes/Kaggle or issuer filings); risk-free rate (FRED U.S. Treasury yields).

4.2.2 Volatility Model

Equity returns 
𝑟
𝑡
r
t
	​

 follow a GARCH(1,1):

𝑟
𝑡
=
𝜇
+
𝜖
𝑡
,
𝜖
𝑡
=
𝜎
𝑡
𝑧
𝑡
,
𝑧
𝑡
∼
𝑁
(
0
,
1
)
r
t
	​

=μ+ϵ
t
	​

,ϵ
t
	​

=σ
t
	​

z
t
	​

,z
t
	​

∼N(0,1)
𝜎
𝑡
2
=
𝜔
+
𝛼
 
𝜖
𝑡
−
1
2
+
𝛽
 
𝜎
𝑡
−
1
2
σ
t
2
	​

=ω+αϵ
t−1
2
	​

+βσ
t−1
2
	​
