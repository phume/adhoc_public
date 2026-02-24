# AML Transaction Monitoring & Anomaly Detection Research
## Retail Bank — Dominican Republic (High-Risk Caribbean Jurisdiction)
### Date: 2026-02-23

---

## Table of Contents
1. [Dominican Republic: Jurisdiction Risk Context](#1-dominican-republic-jurisdiction-risk-context)
2. [Rule-Based Transaction Monitoring by Channel](#2-rule-based-transaction-monitoring-by-channel)
   - 2.1 Cash (Teller Deposits/Withdrawals)
   - 2.2 ATM/ABM
   - 2.3 Cheque
   - 2.4 Wire Transfers
   - 2.5 P2P / Digital Payments
   - 2.6 ACH/EFT
   - 2.7 Foreign Exchange
3. [Anomaly Detection Features for ML Models](#3-anomaly-detection-features-for-ml-models)
   - 3.1 Customer Behavior Features
   - 3.2 Network/Graph Features
   - 3.3 Geographic Features
   - 3.4 Account Features
   - 3.5 Temporal Features
   - 3.6 Peer Group Features
4. [Small Business Specific Rules and Features](#4-small-business-specific-rules-and-features)
5. [FATF / Wolfsberg Group Recommended Scenarios](#5-fatf--wolfsberg-group-recommended-scenarios)
6. [Comprehensive Red Flag & Typology Reference Table](#6-comprehensive-red-flag--typology-reference-table)

---

## 1. Dominican Republic: Jurisdiction Risk Context

### Regulatory Framework
- **Primary AML Law**: Law No. 155-17 on Anti-Money Laundering and Terrorism Financing
- **FIU**: Unidad de Analisis Financiero (UAF), attached to the Ministry of Finance
- **Regional Body**: Member of the Caribbean Financial Action Task Force (CFATF)
- **FATF Status**: Not currently on the FATF grey/black list, but was previously monitored. Risk index score of 4.96 (improving from 6.74 in 2016)

**Sources**:
- [FATF Dominican Republic Country Page](https://www.fatf-gafi.org/en/countries/detail/Dominican-Republic.html)
- [FATF Mutual Evaluation Report - Dominican Republic 2018](https://www.fatf-gafi.org/en/publications/Mutualevaluations/Mer-dominican-republic-2018.html)
- [KnowYourCountry - Dominican Republic](https://www.knowyourcountry.com/country-reports/dominican-republic/)
- [FinCrime Central - AML FX Dominican Republic 2025](https://fincrimecentral.com/aml-foreign-exchange-dominican-republic-2025/)
- [Statista - Money Laundering Risk Index DR](https://www.statista.com/statistics/876092/risk-index-money-laundering-terrorist-financing-dominican-republic/)

### Key Vulnerabilities
| Vulnerability | Description |
|---|---|
| **Drug Transshipment** | DR serves as a cocaine transshipment point from South America to the US/Europe; fentanyl precursors increasingly moving through the region |
| **Bulk Cash Smuggling** | Primary method for moving illicit funds from the US into the DR via couriers |
| **Remittance Corridors** | Wire transfer remittances are a primary channel for illicit fund movement (US-DR corridor) |
| **Currency Exchange Houses** | Casas de cambio facilitate laundering of illicit funds once in the DR |
| **Real Estate & Construction** | Major laundering vehicles within the DR economy |
| **Casinos & Tourism** | Tourism agencies and casinos identified as facilitators |
| **Large Informal Economy** | Weak financial controls in the informal sector |
| **Trade-Based ML** | DR has one of the most rapidly growing TBML exposure rates in the Caribbean |
| **Human Trafficking** | Trafficking routes through the DR create associated financial flows |
| **Corruption** | Government and private sector corruption amplifies all other risks |

**Sources**:
- [US State Department INCSR - Dominican Republic](https://2009-2017.state.gov/j/inl/rls/nrcrpt/2016/vol2/253396.htm)
- [InSight Crime - Drug Ring Exposes Massive Money Laundering in DR](https://insightcrime.org/news/brief/dominican-republic-massive-money-laundering/)
- [Napier AI - Dominican Money Laundering Syndicate](https://www.napier.ai/post/money-laundering-syndicate-kingpin)
- [FinCEN Advisory FIN-2010-A001](https://www.fincen.gov/resources/advisories/fincen-advisory-fin-2010-a001)

---

## 2. Rule-Based Transaction Monitoring by Channel

### 2.1 Cash (Teller Deposits / Withdrawals)

#### Standard Regulatory Thresholds
| Threshold | Description |
|---|---|
| **$10,000 USD** (or local equivalent) | Mandatory CTR filing for any single cash transaction at or above this amount (US standard; DR uses similar threshold under Law 155-17) |
| **$3,000 EUR** | EU AMLR 2024 unified cash threshold |

#### Structuring Detection Rules

| Rule ID | Rule Name | Logic / Threshold | Lookback | Red Flag |
|---|---|---|---|---|
| CASH-001 | **Single Large Cash Deposit** | Single cash deposit >= $10,000 | Real-time | Mandatory CTR trigger |
| CASH-002 | **Aggregate Cash Structuring** | Multiple cash deposits totaling >= $10,000 but each individual deposit < $10,000, same account | 1 business day | Classic structuring to avoid CTR |
| CASH-003 | **Just-Below-Threshold Deposits** | Any cash deposit between $7,000-$9,999 (70-99% of threshold) | Real-time | Potential structuring indicator |
| CASH-004 | **Multi-Day Structuring** | Cumulative cash deposits >= $20,000, each individual deposit < $10,000 | 5 business days (rolling) | Extended structuring pattern |
| CASH-005 | **Smurfing - Multi-Account** | Cash deposits across 3+ accounts by same customer, aggregate >= $10,000 | 1 business day | Smurfing across own accounts |
| CASH-006 | **Smurfing - Multi-Person** | Cash deposits to same account by 3+ different depositors, aggregate >= $10,000 | 3 business days | Third-party smurfing |
| CASH-007 | **Cash-In/Cash-Out Rapid** | Cash deposit followed by cash withdrawal >= 80% of deposit amount | 24-48 hours | Rapid cash movement / pass-through |
| CASH-008 | **Cash Deposit then Wire** | Large cash deposit ($5,000+) followed by international wire transfer | 48-72 hours | Placement followed by layering |
| CASH-009 | **Cash Deposit Velocity Spike** | Cash deposit frequency exceeds 200% of customer's 90-day rolling average | Rolling 7 days vs. 90-day baseline | Behavioral anomaly |
| CASH-010 | **Round Amount Cash Deposits** | Repeated cash deposits in exact round amounts ($5,000, $9,000, $9,500) | 30 days | Structuring indicator |
| CASH-011 | **Branch Hopping** | Cash deposits at 3+ different branches by same customer | 5 business days | Avoiding branch-level detection |
| CASH-012 | **Denomination Anomaly** | Cash deposit with unusual denomination mix (e.g., all small bills for large amount) | Real-time | Drug proceeds indicator |

**Sources**:
- [Ondato - Structuring AML](https://ondato.com/blog/structuring-aml/)
- [AML Network - Deposit Structuring](https://amlnetwork.org/aml-glossary/deposit-structuring/)
- [Facctum - AML Thresholds](https://www.facctum.com/terms/aml-thresholds)
- [Facctum - Structuring vs Smurfing](https://www.facctum.com/blog/structuring-vs-smurfing-in-aml-key-risks-detection-tactics)
- [Focal AI - Smurfing vs Structuring](https://www.getfocal.ai/blog/difference-between-smurfing-and-structuring)
- [Medium - Tuning the Threshold (Karapetyan)](https://medium.com/@georgekar91/tuning-the-threshold-balancing-aml-transaction-monitoring-for-better-detection-65be192c7404)
- [AMLTRIX Framework - ATM Structuring](https://framework.amltrix.com/techniques/T0016.004-atm-structuring)
- [Sanctions.io - AML Transaction Monitoring Rules](https://www.sanctions.io/blog/anti-money-laundering-aml-transaction-monitoring-rules-and-best-practices)

---

### 2.2 ATM / ABM

#### Common Rules

| Rule ID | Rule Name | Logic / Threshold | Lookback | Red Flag |
|---|---|---|---|---|
| ATM-001 | **High-Value ATM Withdrawal** | Single ATM withdrawal at or near daily limit | Real-time | Potential structuring via ATM |
| ATM-002 | **ATM Withdrawal Velocity** | 5+ ATM transactions within 10 minutes from same card | Real-time | Burst withdrawal pattern |
| ATM-003 | **Daily ATM Limit Maximization** | Customer consistently hits daily ATM withdrawal limit | 7 consecutive days | Systematic cash extraction |
| ATM-004 | **Multi-ATM Same Day** | Withdrawals from 5+ different ATMs in single day | 1 day | Geographic dispersion to avoid detection |
| ATM-005 | **ATM Deposit Structuring** | Multiple ATM deposits each < $10,000, aggregate >= $10,000 | 1 business day | Using deposit-capable ATMs to structure |
| ATM-006 | **Geographic Anomaly - Distance** | ATM transactions in locations > 100km apart within short window | 2-4 hours | Impossible travel / card compromise |
| ATM-007 | **Cross-Border ATM Usage** | ATM withdrawals in foreign country inconsistent with customer profile | Real-time | Unexplained cross-border activity |
| ATM-008 | **After-Hours ATM Pattern** | Repeated large ATM transactions between midnight and 5 AM | 30 days | Suspicious timing pattern |
| ATM-009 | **ATM-to-Wire Sequence** | ATM deposits followed by wire transfer from same account | 24-48 hours | Placement-layering sequence |
| ATM-010 | **Dormant Account ATM Activation** | ATM activity on previously dormant account (no activity in 90+ days) | Real-time vs. 90-day history | Dormant account revival |

**Sources**:
- [AMLTRIX Framework - ATM Structuring](https://framework.amltrix.com/techniques/T0016.004-atm-structuring)
- [IBM - AML Transaction Monitoring](https://www.ibm.com/think/topics/aml-transaction-monitoring)
- [Feedzai - AML Transaction Monitoring](https://www.feedzai.com/blog/what-is-aml-transaction-monitoring/)
- [AML Watcher - Fraud Detection Rules](https://amlwatcher.com/blog/fraud-detection-rules/)

---

### 2.3 Cheque

#### Common Rules

| Rule ID | Rule Name | Logic / Threshold | Lookback | Red Flag |
|---|---|---|---|---|
| CHQ-001 | **Cheque Kiting - Cross-Bank** | Cheques drawn on Account A deposited to Account B and vice versa, with no legitimate business purpose | 30 days | Float exploitation / kiting |
| CHQ-002 | **Cheque Kiting - Velocity** | 5+ cheques deposited from different banks in rapid succession, drawn against insufficient funds | 5 business days | Accelerated kiting pattern |
| CHQ-003 | **Remote Deposit Capture - Duplicate** | Same cheque deposited via RDC and physically at a branch or second institution | Real-time | Duplicate deposit fraud |
| CHQ-004 | **Remote Deposit Capture - Volume** | Unusually high volume of RDC deposits (> 200% of customer baseline) | 30 days | Potential fraudulent instrument deposits |
| CHQ-005 | **Third-Party Cheque Deposits** | Cheques payable to third party deposited into customer's own account | Rolling 30 days | Third-party cheque laundering |
| CHQ-006 | **Large Cheque Immediate Withdrawal** | Large cheque deposit followed by cash withdrawal or wire before clearing | 24-48 hours | Fraudulent instrument + rapid cash extraction |
| CHQ-007 | **Sequential Cheque Numbers** | Deposits of money orders or cashier's cheques with sequential serial numbers | 30 days | Bulk purchase of monetary instruments for structuring |
| CHQ-008 | **Cheque Deposit-to-Cash Ratio** | High ratio of cheque deposits immediately converted to cash (> 80%) | 30 days | Pass-through / layering |
| CHQ-009 | **Altered/Washed Cheque** | Cheque instruments flagged for physical alterations (system-detectable via image analysis) | Real-time | Cheque fraud |
| CHQ-010 | **Counter Cheque Abuse** | Excessive use of counter cheques for large transactions | 30 days | Avoiding traceable instruments |

**Sources**:
- [FFIEC BSA/AML - Electronic Banking](https://bsaaml.ffiec.gov/manual/RisksAssociatedWithMoneyLaunderingAndTerroristFinancing/06)
- [TechTarget - AML and Remote Deposit Capture](https://www.techtarget.com/searchcio/tip/How-AML-compliance-applies-to-remote-deposit-capture)
- [Tookitaki - Types of Check Fraud](https://www.tookitaki.com/glossary/check-fraud)
- [DataVisor - Check and Deposit Fraud](https://www.datavisor.com/industry-solutions/check-fraud)
- [FDIC - Risk Management of Remote Deposit Capture](https://www.fdic.gov/news/news/financial/2009/fil09004a.pdf)
- [Abrigo - Check Fraud Detection for AML](https://www.abrigo.com/blog/check-fraud-detection-tips-for-aml-professionals/)
- [AML Network - Remote Deposit Capture](https://amlnetwork.org/aml-glossary/remote-deposit-capture/)

---

### 2.4 Wire Transfers

#### Common Rules

| Rule ID | Rule Name | Logic / Threshold | Lookback | Red Flag |
|---|---|---|---|---|
| WIRE-001 | **Large International Wire** | International wire >= $50,000 (low-risk client) or >= $10,000 (high-risk client) | Real-time | Large value cross-border transfer |
| WIRE-002 | **High-Risk Corridor Wire** | Wire transfer to/from FATF-identified high-risk jurisdiction or non-cooperative country | Real-time | Jurisdictional risk |
| WIRE-003 | **Wire Structuring** | Multiple wires to same beneficiary, each < reporting threshold, aggregate >= threshold | 5 business days | Structuring wire transfers |
| WIRE-004 | **Rapid Wire Velocity** | 5+ wire transfers in 24-72 hours or new beneficiaries added rapidly | 72 hours | Velocity spike / layering |
| WIRE-005 | **Round-Amount Wires** | Wires in exact round amounts ($10,000, $25,000, $50,000) with no apparent commercial basis | 30 days | Non-commercial structured activity |
| WIRE-006 | **Layering - Pass-Through** | Incoming wire immediately followed by outgoing wire of similar amount (pass-through) | 24-48 hours | Layering / funnel account |
| WIRE-007 | **Wire to Shell Company** | Wire to entity in secrecy jurisdiction with no apparent commercial relationship | Real-time | Shell company layering |
| WIRE-008 | **DR-US Corridor Wire** | Wire transfers on US-DR corridor exceeding customer baseline by > 200% | 30 days | High-risk corridor specific to DR operations |
| WIRE-009 | **Fan-Out Pattern** | Single incoming wire split into multiple outgoing wires to different beneficiaries | 24-48 hours | Layering / distribution |
| WIRE-010 | **Fan-In Pattern** | Multiple incoming wires from different originators consolidated into single outgoing wire | 72 hours | Collection / consolidation pattern |
| WIRE-011 | **Wire + Cash Combination** | Cash deposit followed by international wire of similar amount | 48 hours | Placement then integration |
| WIRE-012 | **Incomplete Originator Info** | Wire lacking complete originator or beneficiary information (Travel Rule violation) | Real-time | FATF Recommendation 16 violation |
| WIRE-013 | **Dormant-to-Wire** | Account dormant > 90 days suddenly receives/sends international wire | Real-time | Dormant account exploitation |

**Sources**:
- [FFIEC BSA/AML - Funds Transfers](https://bsaaml.ffiec.gov/manual/RisksAssociatedWithMoneyLaunderingAndTerroristFinancing/07)
- [Sumsub - AML Transaction Monitoring Rules (2025)](https://sumsub.com/blog/aml-transaction-monitoring-rules-scenarios/)
- [Flagright - Developing Effective Transaction Monitoring Rules](https://www.flagright.com/post/developing-effective-transaction-monitoring-rules)
- [Fourthline - Transaction Monitoring in AML](https://www.fourthline.com/glossary/transaction-monitoring)
- [Sumsub - AML Transaction Monitoring 2025 Guide](https://sumsub.com/blog/transaction-monitoring/)

---

### 2.5 P2P / Digital Payments

#### Common Rules

| Rule ID | Rule Name | Logic / Threshold | Lookback | Red Flag |
|---|---|---|---|---|
| P2P-001 | **Rapid P2P Disbursement** | 10+ P2P payments to unique recipients in < 24 hours | 24 hours | Rapid fund dispersal / mule network |
| P2P-002 | **P2P Structuring** | Multiple P2P payments to same recipient, each below threshold, aggregate >= threshold | 5 business days | Structuring via P2P channel |
| P2P-003 | **P2P Collection** | P2P receipts from 10+ unique senders aggregating > $5,000 | 7 days | Unlicensed money transmission / collection |
| P2P-004 | **P2P-to-Wire Chain** | P2P receipts immediately followed by wire transfer of similar aggregate amount | 48 hours | Layering across channels |
| P2P-005 | **New-Account P2P Burst** | New account (< 30 days) with immediate high-volume P2P activity | 30 days from opening | Mule account indicator |
| P2P-006 | **P2P Round Amounts** | Repeated P2P payments in exact round amounts ($500, $1,000, $2,000) | 30 days | Non-organic payment pattern |
| P2P-007 | **Cross-Channel Layering** | P2P receipt -> cash withdrawal -> different P2P send, within short window | 48 hours | Multi-channel layering |
| P2P-008 | **P2P Velocity vs. Baseline** | P2P transaction count or volume exceeds 300% of customer's 90-day rolling average | 7 days vs. 90-day baseline | Behavioral deviation |
| P2P-009 | **Late-Night P2P Activity** | P2P transactions concentrated between midnight-5 AM | 30 days | Suspicious timing pattern |

**Sources**:
- [AMLTRIX Framework - P2P Transfers](https://framework.amltrix.com/techniques/T0134.001)
- [Abrigo - P2P Fraud and AML Trends](https://www.abrigo.com/blog/p2p-fraud-and-emerging-aml-trends/)
- [Sanction Scanner - AML for P2P Industry](https://www.sanctionscanner.com/blog/aml-and-compliance-solution-for-the-peer-2-peer-industry-489)
- [ComplyAdvantage - AML P2P Lending](https://complyadvantage.com/insights/aml-p2p-lending-crowdfunding/)
- [Financial Integrity Institute - AML Challenges for Digital Payments](https://finintegrity.org/from-cash-to-clicks-aml-challenges-typologies-for-digital-payments/)

---

### 2.6 ACH / EFT

#### Common Rules

| Rule ID | Rule Name | Logic / Threshold | Lookback | Red Flag |
|---|---|---|---|---|
| ACH-001 | **Unauthorized Debit** | ACH debit from account with no prior ACH debit history or authorization on file | Real-time | Unauthorized ACH debit fraud |
| ACH-002 | **High-Velocity ACH Credits** | 5+ ACH credits received from unrelated originators in short window | 3 business days | Potential mule account / payroll fraud |
| ACH-003 | **Multiple Unrelated Payroll** | Multiple payroll credits from different employers to single consumer account | 30 days | Payroll fraud indicator / identity theft |
| ACH-004 | **New/Dormant Account + High ACH** | New (< 30 days) or dormant (> 90 days) account receiving high-value ACH credits | Real-time | Mule account exploitation |
| ACH-005 | **ACH Credit then Immediate Withdrawal** | ACH credit received followed by immediate cash withdrawal or wire >= 80% of credit | 24-48 hours | Rapid movement of ACH proceeds |
| ACH-006 | **Return Rate Anomaly** | ACH return/rejection rate > 15% for an originator | Rolling 30 days | Unauthorized debits or fraudulent origination |
| ACH-007 | **SEC Code Mismatch** | ACH transaction SEC code inconsistent with account type (e.g., CCD to personal account) | Real-time | Misuse of corporate payment codes |
| ACH-008 | **Payroll Velocity Spike** | Payroll ACH credit count exceeds 200% of prior 3-month average | Current month vs. 90-day baseline | Potential ghost employee / payroll manipulation |

**Sources**:
- [Nacha - Risk Management (Fraud Monitoring Phase 1)](https://www.nacha.org/rules/risk-management-topics-fraud-monitoring-phase-1)
- [Nacha - Risk Management (Fraud Monitoring Phase 2)](https://www.nacha.org/rules/risk-management-topics-fraud-monitoring-phase-2)
- [FFIEC BSA/AML - ACH Transactions](https://bsaaml.ffiec.gov/manual/RisksAssociatedWithMoneyLaunderingAndTerroristFinancing/08)
- [NICE Actimize - ACH Fraud Detection](https://www.niceactimize.com/blog/fraud-prevention-ach-fraud-the-silent-threat-hiding-in-everyday-transactions)
- [DataVisor - ACH Fraud](https://www.datavisor.com/wiki/automated-clearing-house-fraud)
- [Unit21 - ACH Fraud Protection](https://www.unit21.ai/fraud-aml-dictionary/ach-fraud)
- [Outseer - 2026 Nacha Rule Change](https://www.outseer.com/blog/2026-nacha-rule-change-proactive-fraud-monitoring-requirement)
- [Sardine - New Nacha Rules](https://www.sardine.ai/blog/new-nacha-rules)

---

### 2.7 Foreign Exchange

#### Common Rules

| Rule ID | Rule Name | Logic / Threshold | Lookback | Red Flag |
|---|---|---|---|---|
| FX-001 | **Large FX Transaction** | Currency conversion >= $10,000 equivalent | Real-time | Large FX transaction requiring CDD review |
| FX-002 | **FX Structuring** | Multiple FX conversions each < threshold, aggregate >= threshold | 5 business days | Structuring via FX channel |
| FX-003 | **Unusual Currency Pair** | FX conversion involving non-standard currency pair for customer's stated business | Real-time | Unexplained currency need |
| FX-004 | **Peso Exchange - High Volume** | High-volume DOP/USD or DOP/EUR exchanges inconsistent with stated income or business | 30 days | Potential peso exchange scheme |
| FX-005 | **Round Trip FX** | Currency A -> Currency B -> Currency A with no apparent economic purpose | 30 days | Round-tripping to obscure fund origin |
| FX-006 | **FX + Wire Combination** | FX conversion immediately followed by international wire in converted currency | 48 hours | Placement-layering sequence |
| FX-007 | **Off-Market Rate Tolerance** | Customer accepting FX rate significantly worse than market rate (> 5% spread) | Real-time | Willingness to lose value = laundering indicator |
| FX-008 | **Multiple Casa de Cambio** | Customer transacting FX at multiple exchange houses (where data is shared) | 30 days | Structuring across FX providers |
| FX-009 | **Seasonal FX Anomaly** | FX transaction volume deviates significantly from expected seasonal pattern (e.g., tourism) | Current month vs. same month prior year | Unusual FX activity |

**Sources**:
- [ComplyAdvantage - AML Risks in Foreign Exchange](https://complyadvantage.com/insights/aml-risk-foreign-exchange/)
- [ComplyAdvantage - Money Laundering Through FX Providers](https://complyadvantage.com/insights/money-laundering-through-remittance-fx-providers/)
- [American Express - AML and Currency Exchange](https://www.americanexpress.com/us/foreign-exchange/articles/anti-money-laundering-laws-and-currency-exchange/)
- [AML Watcher - AML Compliance in Remittance and Exchange](https://amlwatcher.com/blog/aml-compliance-in-money-remittance-and-money-exchange/)
- [iDenfy - Money Laundering in Forex Trading](https://www.idenfy.com/blog/forex-trading-aml/)
- [Financial Crime Academy - FX Money Laundering and Remittance](https://financialcrimeacademy.org/fx-money-laundering-and-money-remittance-a-potent-cocktail/)
- [FinCrime Central - AML FX Dominican Republic 2025](https://fincrimecentral.com/aml-foreign-exchange-dominican-republic-2025/)

---

## 3. Anomaly Detection Features for ML Models

### 3.1 Customer Behavior Features

| Feature Name | Description | Computation |
|---|---|---|
| `txn_count_1d / 7d / 30d` | Transaction count over rolling windows | COUNT(txns) in window |
| `txn_amount_sum_1d / 7d / 30d` | Sum of transaction amounts over rolling windows | SUM(amount) in window |
| `txn_amount_avg_30d` | Average transaction amount over 30 days | MEAN(amount) over 30d |
| `txn_amount_std_30d` | Standard deviation of transaction amounts | STD(amount) over 30d |
| `txn_amount_max_30d` | Maximum single transaction in 30 days | MAX(amount) over 30d |
| `txn_amount_zscore` | Z-score of current transaction relative to 90-day history | (current_amt - mean_90d) / std_90d |
| `txn_velocity_ratio` | Ratio of current 7-day velocity to 90-day average | count_7d / (count_90d / ~13) |
| `avg_time_between_txns` | Average time gap between consecutive transactions | MEAN(time_diff between txns) |
| `time_since_last_txn` | Hours/days since last transaction | NOW() - last_txn_timestamp |
| `txn_hour_of_day` | Hour when transaction occurs | EXTRACT(hour from timestamp) |
| `is_off_hours` | Whether transaction occurs outside business hours (8pm-6am) | Boolean flag |
| `weekend_txn_ratio` | Proportion of transactions on weekends vs. weekdays | weekend_count / total_count over 90d |
| `channel_entropy` | Shannon entropy of channel usage distribution | -SUM(p_i * log(p_i)) across channels |
| `channel_shift_flag` | Sudden change in primary channel used | Boolean: new dominant channel in last 7d vs. 90d |
| `cash_to_total_ratio` | Ratio of cash transactions to total transaction volume | cash_amount / total_amount over 30d |
| `debit_credit_ratio` | Ratio of debits to credits | sum_debits / sum_credits over 30d |
| `round_amount_ratio` | Proportion of transactions that are round amounts (multiples of $100, $500, $1000) | round_count / total_count over 30d |
| `just_below_threshold_count` | Number of transactions between 70-99% of reporting threshold | COUNT(txns where amt in [7000, 9999]) over 30d |
| `unique_counterparties_7d / 30d` | Number of unique beneficiaries/originators | COUNT(DISTINCT counterparty) in window |
| `new_counterparty_ratio` | Fraction of recent counterparties that are first-time | new_counterparties_7d / total_counterparties_7d |

**Sources**:
- [Financial Crime Academy - Anomaly Detection in AML Data](https://financialcrimeacademy.org/anomaly-detection-in-aml-data/)
- [IBM - AML Transaction Monitoring](https://www.ibm.com/think/topics/aml-transaction-monitoring)
- [Zencos - A Better Approach to Anomalous Detection for AML](https://www.zencos.com/blog/aml-anomalous-detection-process)
- [idatamax - Anomaly Detection in Financial Transactions](https://idatamax.com/blog/anomaly-detection-finance)
- [DataRobot - AML Alert Scoring](https://docs.datarobot.com/en/docs/get-started/gs-dr5/biz-accelerators/money-launder.html)
- [Hawk AI - AML Transaction Monitoring](https://hawk.ai/solutions/aml/transaction-monitoring)

---

### 3.2 Network / Graph Features

| Feature Name | Description | Computation |
|---|---|---|
| `shared_address_count` | Number of other accounts sharing same registered address | Graph query: COUNT(accounts) at same address |
| `shared_phone_count` | Number of other accounts sharing same phone number | Graph query: COUNT(accounts) with same phone |
| `shared_email_count` | Number of other accounts sharing same email | Graph query |
| `shared_ip_count` | Number of other accounts accessing from same IP | Graph query |
| `shared_beneficiary_count` | Number of other accounts sending to same beneficiary | Graph query on wire/P2P recipients |
| `common_beneficiary_overlap` | Jaccard similarity of beneficiary sets with flagged accounts | |A intersect B| / |A union B| |
| `in_degree_centrality` | Number of unique incoming fund sources | COUNT(DISTINCT originators) |
| `out_degree_centrality` | Number of unique outgoing fund destinations | COUNT(DISTINCT beneficiaries) |
| `betweenness_centrality` | How often account appears on shortest path between other accounts in fund flow | Betweenness centrality algorithm |
| `community_cluster_id` | Community/cluster the account belongs to in the transaction graph | Louvain or similar community detection |
| `fund_flow_circularity` | Whether funds return to originating account within N hops | Cycle detection in directed graph |
| `fan_in_ratio` | Ratio of unique incoming senders to outgoing recipients | in_degree / out_degree |
| `fan_out_ratio` | Ratio of unique outgoing recipients to incoming senders | out_degree / in_degree |
| `layering_depth` | Maximum chain length of sequential transfers from account | Max path length in directed graph |
| `shell_company_score` | Likelihood counterparty is a shell entity (registered in secrecy jurisdiction, nominee directors, etc.) | Composite score from entity attributes |

**Sources**:
- [Linkurious - Graph Analytics and AML: 8 Use Cases](https://linkurious.com/blog/anti-money-laundering-use-cases-graph-analytics/)
- [Oracle - Graph Analytics for AML](https://www.oracle.com/financial-services/aml-financial-crime-compliance/graph-analytics-powers-the-game/)
- [McKinsey - Network Analytics and the Fight Against Money Laundering](https://www.mckinsey.com/industries/financial-services/our-insights/banking-matters/network-analytics-and-the-fight-against-money-laundering)
- [Monocle Solutions - Graph Technology and AML](https://www.monoclesolutions.com/en-za/insights/graph-technology-and-aml)
- [NICE Actimize - Graph Analytics for AML (eBook)](https://www.niceactimize.com/Lists/Ebooks/aml_graph_analytics_for_aml_insights_ebook_2021.pdf)
- [TigerGraph - Anti-Money Laundering](https://www.tigergraph.com/solutions/anti-money-laundering-aml/)
- [Medium (Jason Wu) - Network Analysis for AML with Python](https://medium.com/@jasonclwu/network-analysis-for-anti-money-laundering-with-python-ad981792a947)
- [ScienceDirect - Complex Networks-Based Anomaly Detection for AML](https://www.sciencedirect.com/science/article/abs/pii/S2666281725001453)

---

### 3.3 Geographic Features

| Feature Name | Description | Computation |
|---|---|---|
| `high_risk_jurisdiction_flag` | Transaction involves FATF-listed or bank-defined high-risk country | Boolean from country risk lookup |
| `high_risk_jurisdiction_count_30d` | Number of transactions involving high-risk jurisdictions in 30 days | COUNT(txns) with high-risk country |
| `cross_border_ratio` | Ratio of cross-border transactions to domestic | cross_border_count / total_count over 30d |
| `unique_countries_30d` | Number of unique countries involved in transactions | COUNT(DISTINCT country) over 30d |
| `atm_location_entropy` | Diversity of ATM locations used (high entropy = many locations) | Shannon entropy of ATM location distribution |
| `atm_max_distance_km` | Maximum distance between ATM transactions in a day | Haversine distance between ATM coordinates |
| `impossible_travel_flag` | ATM/login locations that are geographically impossible given time window | Boolean: distance / time > plausible speed |
| `ip_geolocation_mismatch` | IP location inconsistent with customer's registered address or usual location | Boolean |
| `ip_country_changes_30d` | Number of distinct IP countries in 30 days | COUNT(DISTINCT ip_country) |
| `dr_us_corridor_volume` | Volume of DR-to-US or US-to-DR transactions | SUM(amount) on DR-US corridor |
| `remittance_corridor_ratio` | Ratio of remittance-corridor transactions to total | corridor_volume / total_volume |
| `branch_location_anomaly` | Transaction at branch far from customer's registered address / usual branch | Distance > threshold |

**Sources**:
- [FFIEC BSA/AML - Funds Transfers](https://bsaaml.ffiec.gov/manual/RisksAssociatedWithMoneyLaunderingAndTerroristFinancing/07)
- [Feedzai - AML Transaction Monitoring](https://www.feedzai.com/blog/what-is-aml-transaction-monitoring/)
- [Sanctions.io - AML Transaction Monitoring Rules](https://www.sanctions.io/blog/anti-money-laundering-aml-transaction-monitoring-rules-and-best-practices)

---

### 3.4 Account Features

| Feature Name | Description | Computation |
|---|---|---|
| `account_age_days` | Days since account was opened | NOW() - account_open_date |
| `is_new_account` | Account less than 90 days old | Boolean |
| `is_dormant_reactivated` | Account was dormant (> 90 days no activity) and recently reactivated | Boolean |
| `product_count` | Number of products held (chequing, savings, credit, loan) | COUNT(products) |
| `product_mix_risk_score` | Risk score based on product combination | Lookup table or model |
| `expected_monthly_volume` | Expected monthly volume based on CDD/KYC profile | From onboarding data |
| `actual_vs_expected_ratio` | Ratio of actual activity to expected activity | actual_volume / expected_volume |
| `balance_avg_30d` | Average daily balance over 30 days | MEAN(daily_balance) |
| `balance_volatility` | Standard deviation of daily balance / mean balance | STD(daily_balance) / MEAN(daily_balance) |
| `balance_spike_flag` | Balance exceeds 500% of 90-day average | Boolean |
| `credit_utilization` | Credit card / line of credit utilization | outstanding / limit |
| `overdraft_frequency_30d` | Number of overdraft events in 30 days | COUNT(overdraft_events) |
| `pep_flag` | Customer is a Politically Exposed Person | Boolean from screening |
| `sanctions_proximity_score` | Degree of name/entity match to sanctions lists | Fuzzy match score |
| `adverse_media_flag` | Customer associated with negative news | Boolean from screening |
| `risk_rating` | Customer's current risk rating (low/medium/high/critical) | From CDD system |
| `sar_history_count` | Number of prior SARs filed on this customer | COUNT(historical_sars) |

**Sources**:
- [Sumsub - AML Transaction Monitoring (2025)](https://sumsub.com/blog/transaction-monitoring/)
- [Flagright - Understanding FATF Recommendations](https://www.flagright.com/post/understanding-fatf-recommendations-for-aml-compliance)
- [Persona - AML Transaction Monitoring](https://withpersona.com/blog/what-is-aml-transaction-monitoring-and-how-is-it-set-up)

---

### 3.5 Temporal Features

| Feature Name | Description | Computation |
|---|---|---|
| `day_of_week` | Day of week (0=Monday, 6=Sunday) | EXTRACT(dow from timestamp) |
| `is_weekend` | Whether transaction falls on Saturday/Sunday | Boolean |
| `is_holiday` | Whether transaction falls on DR public holiday | Boolean from holiday calendar |
| `hour_of_day` | Hour of day (0-23) | EXTRACT(hour from timestamp) |
| `time_of_day_bucket` | Bucketed: morning/afternoon/evening/night | Categorical |
| `month_of_year` | Month (1-12) for seasonality | EXTRACT(month from timestamp) |
| `is_month_end` | Last 3 business days of month (salary/payroll period) | Boolean |
| `is_tax_season` | Transaction during known tax filing period | Boolean |
| `days_since_account_open` | Days elapsed since account opening | NOW() - open_date |
| `burst_score` | Number of transactions in last 1 hour relative to typical hourly rate | count_1h / avg_hourly_count_90d |
| `inter_transaction_time_cv` | Coefficient of variation of time between transactions | STD(inter_txn_time) / MEAN(inter_txn_time) |
| `activity_trend_slope` | Slope of weekly transaction volume over last 12 weeks | Linear regression slope |
| `seasonal_deviation` | Current month volume vs. same month prior year | current_month_vol / prior_year_same_month_vol |
| `recency_of_first_txn` | How recently the customer made their very first transaction | Days since first transaction |

**Sources**:
- [Financial Crime Academy - Anomaly Detection in AML Data](https://financialcrimeacademy.org/anomaly-detection-in-aml-data/)
- [Anomalo - ML Approaches to Time Series Anomaly Detection](https://www.anomalo.com/blog/machine-learning-approaches-to-time-series-anomaly-detection/)
- [Xenonstack - Anomaly Detection with Time Series Forecasting](https://www.xenonstack.com/blog/time-series-deep-learning)

---

### 3.6 Peer Group Features

| Feature Name | Description | Computation |
|---|---|---|
| `peer_group_id` | Assigned peer group (by industry, geography, account type) | Clustering algorithm or rule-based assignment |
| `peer_txn_volume_percentile` | Customer's transaction volume percentile within peer group | PERCENTILE_RANK within group |
| `peer_txn_count_percentile` | Customer's transaction count percentile within peer group | PERCENTILE_RANK within group |
| `peer_cash_ratio_deviation` | Deviation of customer's cash ratio from peer group median | (customer_cash_ratio - peer_median) / peer_std |
| `peer_avg_txn_deviation` | Deviation of average transaction size from peer group | (customer_avg - peer_avg) / peer_std |
| `peer_channel_mix_distance` | Distance of channel usage distribution from peer group centroid | KL divergence or cosine distance |
| `peer_wire_ratio_deviation` | Deviation of wire transfer proportion from peer group norm | Z-score within peer group |
| `peer_counterparty_count_deviation` | Deviation of unique counterparty count from peer group | Z-score within peer group |
| `peer_dormancy_deviation` | Whether account dormancy pattern deviates from peer group | Boolean based on peer comparison |
| `archetype_misalignment_score` | Soft-clustering misalignment score from behavioral archetype model | Bayesian archetype model output |

**Peer Group Segmentation Dimensions (for assigning peer groups)**:
- **Industry/NAICS code** (for business accounts)
- **Geographic region** (province/municipality within DR)
- **Account type** (personal chequing, savings, business operating, etc.)
- **Annual revenue band** (for business accounts)
- **Customer tenure band**
- **Risk rating**

**Sources**:
- [Solytics Partners - Peer Group Analysis for AML Transaction Monitoring](https://www.solytics-partners.com/resources/case-studies/peer-group-analysis-for-aml-transaction-monitoring)
- [FICO - Using AI and ML to Improve AML](https://www.fico.com/blogs/using-ai-and-machine-learning-improve-aml)
- [Google Cloud - Anti Money Laundering AI](https://cloud.google.com/anti-money-laundering-ai)
- [MIT - AI-Based Industry Peer Grouping System](https://dspace.mit.edu/bitstream/handle/1721.1/143561/2022_PeerGrouping_JFDS.pdf)
- [ABS Singapore - Data Analytics and ML for AML/CFT](https://abs.org.sg/docs/library/acip-industry-perspectives-on-best-practices---leveraging-on-data-analytics-and-machine-learning-methods-for-amlcft.pdf)

---

## 4. Small Business Specific Rules and Features

### 4.1 Cash-Intensive Business Monitoring

Cash-intensive industries requiring enhanced monitoring:
- Restaurants, bars, nightclubs
- Retail stores, convenience stores
- Gas stations / fuel distributors
- Liquor stores, cigarette distributors
- Car washes
- Laundromats
- Parking garages
- Privately owned ATM operators
- Street vendors / market sellers (relevant to DR informal economy)

#### Rules for Cash-Intensive Businesses

| Rule ID | Rule Name | Logic / Threshold | Lookback | Red Flag |
|---|---|---|---|---|
| SMB-001 | **Cash Deposit vs. Industry Peer** | Cash deposits exceed 200% of industry peer group average for same business type | 30 days | Significantly higher cash than comparable businesses |
| SMB-002 | **Cash Deposit Consistency** | Cash deposits show unnatural consistency (e.g., exact same amount daily) | 30 days | Real businesses have variability |
| SMB-003 | **Revenue vs. Location** | Revenue inconsistent with business location demographics (e.g., high-revenue restaurant in low-traffic area) | Quarterly | Location-revenue mismatch |
| SMB-004 | **Cash-to-Revenue Ratio** | Cash deposits exceed expected cash ratio for business type (e.g., > 90% for a restaurant with card terminal) | 30 days | Over-reporting cash sales |
| SMB-005 | **Seasonal Revenue Anomaly** | Revenue pattern doesn't follow expected seasonal trends for business type | 12-month comparison | Counter-seasonal revenue |

**Sources**:
- [FFIEC BSA/AML - Cash-Intensive Businesses](https://bsaaml.ffiec.gov/manual/RisksAssociatedWithMoneyLaunderingAndTerroristFinancing/29)
- [FFIEC BSA/AML - Persons and Entities: Cash-Intensive Businesses](https://bsaaml.ffiec.gov/manual/PersonsAndEntities/08)
- [AML Watcher - AML Guide for Cash-Intensive Businesses](https://amlwatcher.com/blog/anti-money-laundering-aml-guide-for-cash-intensive-businesses/)
- [RapidAML - Money Laundering Risks in Cash-Intensive Businesses](https://rapidaml.com/articles/money-laundering-risks-in-cash-intensive-businesses/)
- [Financial Crime Academy - Red Flags in High-Risk Industries](https://financialcrimeacademy.org/red-flags-in-high-risk-industries/)
- [First AML - Cash-Intensive Businesses Red Flags](https://www.firstaml.com/resources/cash-intensive-businesses-and-their-red-flags/)

### 4.2 Revenue Consistency Checks

| Rule ID | Rule Name | Logic / Threshold | Lookback | Red Flag |
|---|---|---|---|---|
| SMB-006 | **Revenue Spike** | Monthly revenue exceeds 300% of trailing 6-month average | Monthly vs. 6-month baseline | Sudden unexplained revenue increase |
| SMB-007 | **Revenue vs. Tax Filings** | Declared bank revenue significantly deviates from tax filings (where accessible) | Annual | Revenue mismatch |
| SMB-008 | **Revenue vs. Employee Count** | Revenue per employee significantly exceeds industry benchmark | Quarterly | Inflated revenue per head |
| SMB-009 | **Weekend/Holiday Revenue** | Cash deposits on weekends/holidays when business is expected to be closed | Rolling 90 days | Deposits when business should be inactive |
| SMB-010 | **No Expense Pattern** | Business account shows deposits but minimal business-related expenses (rent, utilities, supplies) | 90 days | Potential shell business |

### 4.3 Payroll Anomalies

| Rule ID | Rule Name | Logic / Threshold | Lookback | Red Flag |
|---|---|---|---|---|
| SMB-011 | **Payroll Count vs. Business Size** | Payroll disbursements exceed reasonable employee count for business type | Monthly | Ghost employees |
| SMB-012 | **Payroll to Related Parties** | Payroll payments going to accounts owned by business owner or family members | Ongoing | Self-dealing / fund extraction |
| SMB-013 | **Payroll Amount Anomaly** | Individual payroll amounts significantly exceed industry norms | Monthly | Suspicious payroll disbursement |
| SMB-014 | **Payroll Timing Irregularity** | Payroll not aligned with standard pay cycles (bi-weekly, monthly) | 90 days | Irregular "payroll" as disguised transfers |
| SMB-015 | **New Payroll Recipient Spike** | Sudden addition of 5+ new payroll recipients | Monthly | Potential mule accounts added as "employees" |

### 4.4 Vendor Payment Patterns

| Rule ID | Rule Name | Logic / Threshold | Lookback | Red Flag |
|---|---|---|---|---|
| SMB-016 | **New Vendor Spike** | 5+ new vendor payees added in a single month | 30 days | Potential fictitious vendor payments |
| SMB-017 | **Vendor in High-Risk Jurisdiction** | Payments to vendors in FATF high-risk jurisdictions | Real-time | Jurisdictional risk |
| SMB-018 | **Round Amount Vendor Payments** | Vendor payments in exact round amounts lacking invoice-level precision | 30 days | Potentially fabricated invoices |
| SMB-019 | **Vendor Payment Concentration** | > 80% of expenses going to single vendor | 90 days | Potential related-party or shell vendor |
| SMB-020 | **Vendor Payment then Cash Back** | Vendor payment followed by cash deposit of similar amount (kickback pattern) | 7 days | Round-tripping through vendors |

### 4.5 Commingling of Personal and Business Funds

| Rule ID | Rule Name | Logic / Threshold | Lookback | Red Flag |
|---|---|---|---|---|
| SMB-021 | **Personal-to-Business Transfer** | Frequent transfers between owner's personal account and business account with no clear business purpose | 30 days | Fund commingling |
| SMB-022 | **Business Account Personal Expenses** | Business account used for personal expenses (e.g., personal shopping, personal travel) | 30 days | Misuse of business account |
| SMB-023 | **Cash Extraction Pattern** | Business deposits followed by personal account withdrawals of similar amounts | 48 hours | Using business as pass-through |
| SMB-024 | **Multi-Business Intermingling** | Same owner has multiple business accounts with frequent inter-account transfers lacking commercial purpose | 30 days | Layering across own businesses |
| SMB-025 | **Personal Account as Business** | Individual/personal account receiving structured cash deposits with business-like patterns | 90 days | Operating unregistered business through personal account |

**Sources**:
- [FFIEC BSA/AML - Appendix F: Red Flags](https://bsaaml.ffiec.gov/manual/Appendices/07)
- [AML Watcher - Commingling](https://amlwatcher.com/blog/how-commingling-blur-the-lines-between-legitimate-illegal-wealth/)
- [ComplyAdvantage - AML Red Flags](https://complyadvantage.com/insights/aml-red-flags/)
- [Financial Crime Academy - AML Red Flags](https://financialcrimeacademy.org/aml-red-flags-2/)
- [KYC Hub - AML Red Flags](https://www.kychub.com/blog/top-aml-red-flags/)
- [Financial Integrity Institute - AML for Small Businesses](https://finintegrity.org/aml-compliance-for-small-businesses/)
- [Financial Crime Academy - AML Regulations and Small Businesses](https://financialcrimeacademy.org/aml-regulations-and-small-businesses/)

---

## 5. FATF / Wolfsberg Group Recommended Scenarios

### 5.1 FATF Recommended Monitoring Scenarios

The FATF 40 Recommendations (particularly Recommendations 10, 11, 16, 20) establish the following monitoring expectations:

| # | Scenario Category | Description | FATF Rec. |
|---|---|---|---|
| 1 | **Structuring / Threshold Avoidance** | Transactions deliberately split to avoid reporting thresholds | R.20 |
| 2 | **Unusual Transaction Size** | Transactions that are unusually large relative to customer profile | R.10, R.20 |
| 3 | **Rapid Fund Movement** | Funds deposited and immediately transferred out | R.20 |
| 4 | **High-Risk Jurisdiction Activity** | Transactions involving countries with weak AML/CFT regimes | R.19 |
| 5 | **Politically Exposed Persons (PEP)** | Enhanced monitoring of PEPs and their associates | R.12 |
| 6 | **Unusual Business Activity** | Activity inconsistent with customer's stated business | R.10, R.20 |
| 7 | **Complex/Unusual Transaction Patterns** | Transactions with no apparent economic or commercial purpose | R.20 |
| 8 | **Virtual Asset Structuring** | Micro-transfers via crypto/virtual assets to avoid thresholds (2025 update) | R.15 |
| 9 | **Trade-Based Money Laundering** | Over/under-invoicing, phantom shipments, multi-invoicing | R.20 |
| 10 | **Correspondent Banking Risk** | Nested relationships, payable-through accounts | R.13 |
| 11 | **Wire Transfer Travel Rule** | Incomplete originator/beneficiary information in wire transfers | R.16 |
| 12 | **Cash-Intensive Business Monitoring** | Enhanced scrutiny of high-cash businesses | R.20 |
| 13 | **Terrorism Financing Indicators** | Small, structured transactions potentially linked to terrorism | R.20 (Special Rec.) |
| 14 | **Proliferation Financing** | Transactions that may finance WMD proliferation | R.7 |

**2024-2025 Emerging FATF Focus Areas**:
- Stablecoins and decentralized finance (DeFi)
- Cross-chain bridges and mixers
- Refund abuse as a laundering cover
- Mobile behavioral analytics linked to AML monitoring
- Ransomware payment flows

**Sources**:
- [Flagright - Understanding FATF Recommendations](https://www.flagright.com/post/understanding-fatf-recommendations-for-aml-compliance)
- [FATF Black and Grey Lists](https://www.fatf-gafi.org/en/countries/black-and-grey-lists.html)
- [Partisia - FATF Recommendations AML & CTF Standards](https://www.partisia.com/blog/fatf-recommendations-applying-global-aml-and-ctf-standards-across-financial-institutions)
- [FinRegE - FATF 2025 Guidance](https://finreg-e.com/fatfs-2025-guidance-smarter-aml-cft-compliance/)
- [Silent Eight - 2025 AML Trends](https://www.silenteight.com/blog/2025-trends-in-aml-and-financial-crime-compliance-as-we-enter-q4)
- [Flagright - Regulatory Changes in AML 2025](https://www.flagright.com/post/regulatory-changes-in-aml-compliance)

### 5.2 Wolfsberg Group Monitoring Framework

The Wolfsberg Group (13 global banks) published key guidance in 2024 and 2025:

#### Wolfsberg Statement on Effective Monitoring (2024) - Key Principles

| Principle | Description |
|---|---|
| **Risk-Based Approach** | Monitoring scenarios calibrated to institution-specific risk (not one-size-fits-all thresholds) |
| **Beyond Transaction Monitoring** | Monitor customer behavior and attributes, not just individual transactions -- "MSA" (Monitoring for Suspicious Activity) is broader than TM |
| **Peer Group Analytics** | Incorporate dynamic peer group comparisons and spending pattern analysis |
| **Quality Over Quantity** | Prioritize quality of alerts over volume; reduce false positives to focus investigator effort |
| **Feedback Loops** | Establish feedback loops between FIs and regulators; use law enforcement outcomes to refine monitoring |
| **False Negative Analysis** | Assess SARs/STRs generated from sources other than automated monitoring (internal referrals, law enforcement) to identify monitoring gaps |
| **Innovation Transition** | Move from purely rules-based to AI/ML-augmented monitoring (2025 Part II statement) |
| **Data Quality** | Improve quality and dynamism of captured data points for better monitoring accuracy |

#### Wolfsberg Statement Part II: Transitioning to Innovation (2025)

| Focus Area | Description |
|---|---|
| **AI/ML Integration** | Financial institutions should progressively integrate machine learning models alongside traditional rules |
| **Explainability** | ML models must maintain explainability for regulatory examination and SAR narrative support |
| **Continuous Calibration** | Models require ongoing calibration, back-testing, and validation |
| **Holistic Customer View** | Combine transactional data, KYC data, screening results, and behavioral analytics |

**Sources**:
- [Wolfsberg Group - Statement on Effective Monitoring (2024)](https://wolfsberg-group.org/resources/168/)
- [Wolfsberg Group - Statement Part II: Transitioning to Innovation (2025)](https://wolfsberg-group.org/resources/202/)
- [Wolfsberg Group - Official PDF 2024](https://www.moneylaunderingnews.com/wp-content/uploads/sites/12/2024/07/Wolfsberg-Group-MSA-Statement-for-publication.pdf)
- [Wolfsberg Group - Official PDF 2025](https://financialcrime.lu/assets/pdfs/articles/2025/08/20250827%20EN%20Statement%20on%20Effective%20Monitoring%20for%20Suspicious%20Activity%20%C2%A6%20Part%20II%20-%20Transitioning%20to%20Innovation_%5BMD5_F987A8AB6D2B85A2FACE6FDE74F704CD%5D.pdf)
- [Sanctions.io - Wolfsberg AML Principles Overview](https://www.sanctions.io/blog/wolfsberg-aml-principles)
- [Facctum - Wolfsberg Group](https://www.facctum.com/terms/wolfsberg-group)
- [TFG - Wolfsberg Guidance on Effective Monitoring](https://www.tradefinanceglobal.com/posts/the-wolfsberg-group-releases-new-guidance-monitoring-suspicious-activity/)

### 5.3 FFIEC BSA/AML Examination Manual - Key Monitoring Components

The FFIEC manual (Appendix S) identifies these key suspicious activity monitoring components that examiners evaluate:

| Component | Description |
|---|---|
| **Customer Identification & Risk Rating** | CIP, CDD, EDD processes feeding risk scores into monitoring |
| **Transaction Monitoring** | Automated systems detecting unusual patterns across all product lines |
| **Watch List Filtering** | Real-time screening against OFAC, UN, EU, and local sanctions lists |
| **SAR/STR Filing** | Processes for investigating alerts and filing suspicious activity reports |
| **Cash Reporting** | CTR filing and cash aggregation across branches |
| **Risk Assessment** | Enterprise-wide AML risk assessment informing monitoring coverage |
| **Independent Testing** | Regular audit of monitoring system effectiveness |
| **Training** | Staff training on red flags and escalation procedures |

**FFIEC Red Flag Categories (Appendix F)**:
- Potential Money Laundering Activity related to accounts
- Potential Money Laundering Activity related to cash transactions
- Potential Money Laundering Activity related to wire/funds transfers
- Potential Money Laundering Activity related to trade finance
- Potential Money Laundering Activity related to real estate
- Potential Money Laundering Activity related to lending activities
- Potential Terrorist Financing indicators

**Sources**:
- [FFIEC BSA/AML Examination Manual](https://bsaaml.ffiec.gov/manual)
- [FFIEC Appendix F - Red Flags](https://bsaaml.ffiec.gov/manual/Appendices/07)
- [FFIEC Appendix S - Key Suspicious Activity Monitoring Components](https://bsaaml.ffiec.gov/manual/Appendices/20)
- [FFIEC Appendix K - Customer Risk vs. Due Diligence](https://bsaaml.ffiec.gov/manual/Appendices/12)
- [OCC Bulletin 2023-26 - Updated BSA/AML Manual](https://www.occ.gov/news-issuances/bulletins/2023/bulletin-2023-26.html)

---

## 6. Comprehensive Red Flag & Typology Reference Table

The following table consolidates all identified red flags and AML risk typologies with source references, descriptions, potential rule-based Python function signatures, and potential anomaly detection feature engineering functions.

| # | Red Flag / Typology | Source Reference | Description | Rule-Based Python Function | Anomaly Detection Feature Function |
|---|---|---|---|---|---|
| 1 | **Cash Structuring (Single Account)** | [FFIEC Appendix F](https://bsaaml.ffiec.gov/manual/Appendices/07), [Ondato](https://ondato.com/blog/structuring-aml/) | Multiple cash deposits below reporting threshold aggregating above threshold within a day | `def detect_cash_structuring(txns, threshold=10000, window_days=1): return sum([t.amount for t in txns if t.channel=='CASH' and t.date in window]) >= threshold and all(t.amount < threshold for t in txns)` | `def feat_just_below_threshold_count(txns, threshold=10000, pct_low=0.7): return len([t for t in txns if t.amount >= threshold*pct_low and t.amount < threshold])` |
| 2 | **Smurfing (Multi-Person)** | [Facctum](https://www.facctum.com/blog/structuring-vs-smurfing-in-aml-key-risks-detection-tactics), [Focal AI](https://www.getfocal.ai/blog/difference-between-smurfing-and-structuring) | Multiple individuals making deposits to same account, aggregate >= threshold | `def detect_smurfing(deposits, acct, threshold=10000, window_days=3): depositors = set(d.depositor for d in deposits); return len(depositors)>=3 and sum(d.amount for d in deposits)>=threshold` | `def feat_unique_depositors_count(deposits, window_days=3): return len(set(d.depositor_id for d in deposits))` |
| 3 | **Rapid Cash Movement** | [Sanctions.io](https://www.sanctions.io/blog/anti-money-laundering-aml-transaction-monitoring-rules-and-best-practices) | Cash deposit immediately followed by wire/transfer of similar amount | `def detect_cash_then_wire(txns, hours=48, match_pct=0.8): cash_deps = [t for t in txns if t.type=='CASH_DEP']; wires = [t for t in txns if t.type=='WIRE_OUT']; return any(w.amount >= c.amount*match_pct and (w.time-c.time).hours<=hours for c in cash_deps for w in wires)` | `def feat_cash_to_wire_time_gap(txns): # min hours between cash deposit and subsequent wire` |
| 4 | **Branch Hopping** | [FFIEC Appendix F](https://bsaaml.ffiec.gov/manual/Appendices/07) | Cash deposits at multiple different branches in short period | `def detect_branch_hopping(txns, min_branches=3, window_days=5): branches = set(t.branch_id for t in txns if t.channel=='CASH'); return len(branches) >= min_branches` | `def feat_unique_branches_used(txns, window_days=5): return len(set(t.branch_id for t in txns))` |
| 5 | **ATM Structuring** | [AMLTRIX](https://framework.amltrix.com/techniques/T0016.004-atm-structuring) | Deposits via deposit-capable ATMs structured below threshold | `def detect_atm_structuring(txns, threshold=10000, window_days=1): atm_deps = [t for t in txns if t.channel=='ATM' and t.type=='DEPOSIT']; return sum(t.amount for t in atm_deps)>=threshold and all(t.amount<threshold for t in atm_deps)` | `def feat_atm_deposit_aggregate_ratio(txns, threshold=10000): return sum(t.amount for t in atm_txns) / threshold` |
| 6 | **Impossible Travel (ATM)** | [Feedzai](https://www.feedzai.com/blog/what-is-aml-transaction-monitoring/) | ATM transactions in geographically distant locations within impossibly short time | `def detect_impossible_travel(txns, max_speed_kmh=500): for t1, t2 in consecutive_pairs(atm_txns): dist = haversine(t1.loc, t2.loc); time_h = (t2.time-t1.time).hours; if dist/time_h > max_speed_kmh: return True` | `def feat_max_atm_velocity_kmh(txns): # max km/h between consecutive ATM txns` |
| 7 | **Wire to High-Risk Jurisdiction** | [FFIEC Funds Transfers](https://bsaaml.ffiec.gov/manual/RisksAssociatedWithMoneyLaunderingAndTerroristFinancing/07) | Wire transfers to/from FATF-listed countries or sanctioned jurisdictions | `def detect_high_risk_wire(txn, high_risk_countries): return txn.type=='WIRE' and (txn.dest_country in high_risk_countries or txn.orig_country in high_risk_countries)` | `def feat_high_risk_country_wire_ratio(txns, high_risk_countries): return count_hr_wires / total_wires` |
| 8 | **Layering / Pass-Through** | [Sumsub](https://sumsub.com/blog/aml-transaction-monitoring-rules-scenarios/), [Fourthline](https://www.fourthline.com/glossary/transaction-monitoring) | Incoming funds immediately transferred out to different account(s) | `def detect_passthrough(txns, hours=48, match_pct=0.8): credits = get_credits(txns); debits = get_debits(txns); return any(d.amount>=c.amount*match_pct and (d.time-c.time).hours<=hours for c in credits for d in debits)` | `def feat_passthrough_ratio(txns): return sum_outflows_within_48h / sum_inflows` |
| 9 | **Fan-Out Pattern** | [Flagright](https://www.flagright.com/post/developing-effective-transaction-monitoring-rules) | One large incoming transfer split into many smaller outgoing transfers | `def detect_fan_out(txns, min_recipients=3, hours=48): incoming = max_credit(txns); outgoing = [t for t in txns if t.type=='DEBIT' and within_hours(t, incoming, hours)]; return len(set(t.beneficiary for t in outgoing)) >= min_recipients` | `def feat_fan_out_ratio(txns): return out_degree / in_degree` |
| 10 | **Fan-In Pattern** | [Flagright](https://www.flagright.com/post/developing-effective-transaction-monitoring-rules) | Multiple incoming transfers from different sources consolidated into one outgoing | `def detect_fan_in(txns, min_senders=3, hours=72): credits = get_credits(txns); if len(set(c.originator for c in credits))>=min_senders: outgoing = get_subsequent_debit(txns); return outgoing is not None` | `def feat_fan_in_ratio(txns): return in_degree / out_degree` |
| 11 | **Round Amount Transactions** | [Sumsub](https://sumsub.com/blog/aml-transaction-monitoring-rules-scenarios/) | Repeated transactions in exact round amounts | `def detect_round_amounts(txns, round_unit=1000, min_count=3, window_days=30): round_txns = [t for t in txns if t.amount % round_unit == 0]; return len(round_txns) >= min_count` | `def feat_round_amount_ratio(txns): return count_round / count_total` |
| 12 | **Dormant Account Reactivation** | [IBM](https://www.ibm.com/think/topics/aml-transaction-monitoring) | Previously inactive account suddenly shows significant activity | `def detect_dormant_reactivation(acct, txns, dormant_days=90): last_txn_date = max(t.date for t in historical_txns); return (today - last_txn_date).days > dormant_days and len(recent_txns) > 0` | `def feat_days_since_last_activity(acct): return (now - last_txn_date).days` |
| 13 | **Cheque Kiting** | [Tookitaki](https://www.tookitaki.com/glossary/check-fraud), [Abrigo](https://www.abrigo.com/blog/check-fraud-detection-tips-for-aml-professionals/) | Exploiting float time between multiple accounts at different banks | `def detect_cheque_kiting(txns, accts): cross_bank_cheques = [t for t in txns if t.type=='CHEQUE_DEP' and t.drawn_on_bank != home_bank]; return has_circular_pattern(cross_bank_cheques, accts)` | `def feat_cheque_deposit_velocity(txns): return count_cheque_deposits_per_week` |
| 14 | **Remote Deposit Duplicate** | [TechTarget](https://www.techtarget.com/searchcio/tip/How-AML-compliance-applies-to-remote-deposit-capture), [AML Network](https://amlnetwork.org/aml-glossary/remote-deposit-capture/) | Same cheque deposited via RDC and at branch | `def detect_rdc_duplicate(rdc_deposits, branch_deposits): return any(match_cheque_image(r, b) for r in rdc_deposits for b in branch_deposits)` | `def feat_rdc_to_branch_deposit_ratio(txns): return rdc_count / branch_count` |
| 15 | **P2P Rapid Disbursement** | [AMLTRIX](https://framework.amltrix.com/techniques/T0134.001), [Abrigo](https://www.abrigo.com/blog/p2p-fraud-and-emerging-aml-trends/) | High volume P2P payments to many unique recipients in short time | `def detect_p2p_rapid_disbursement(txns, min_recipients=10, hours=24): p2p = [t for t in txns if t.channel=='P2P' and t.type=='SEND']; return len(set(t.recipient for t in p2p)) >= min_recipients` | `def feat_p2p_unique_recipients_24h(txns): return count_distinct_recipients` |
| 16 | **Unauthorized ACH Debit** | [FFIEC ACH](https://bsaaml.ffiec.gov/manual/RisksAssociatedWithMoneyLaunderingAndTerroristFinancing/08), [Nacha](https://www.nacha.org/rules/risk-management-topics-fraud-monitoring-phase-1) | ACH debit with no authorization history or from unfamiliar originator | `def detect_unauthorized_ach(txn, acct): return txn.type=='ACH_DEBIT' and txn.originator not in acct.authorized_originators` | `def feat_new_ach_originator_flag(txn, acct): return txn.originator not in historical_originators` |
| 17 | **Ghost Employee Payroll** | [Nacha Phase 2](https://www.nacha.org/rules/risk-management-topics-fraud-monitoring-phase-2) | Multiple payroll credits from different employers to single personal account | `def detect_ghost_payroll(txns): payroll = [t for t in txns if t.sec_code=='PPD']; employers = set(t.originator for t in payroll); return len(employers) >= 3` | `def feat_distinct_payroll_sources(txns): return count_distinct_employers` |
| 18 | **FX Structuring** | [ComplyAdvantage FX](https://complyadvantage.com/insights/aml-risk-foreign-exchange/) | Multiple FX conversions each below threshold | `def detect_fx_structuring(txns, threshold=10000, window_days=5): fx_txns = [t for t in txns if t.channel=='FX']; return sum(t.amount for t in fx_txns)>=threshold and all(t.amount<threshold for t in fx_txns)` | `def feat_fx_aggregate_vs_threshold(txns, threshold): return sum_fx_amount / threshold` |
| 19 | **Peso Exchange Scheme** | [FinCrime Central DR](https://fincrimecentral.com/aml-foreign-exchange-dominican-republic-2025/), [FinCEN](https://www.fincen.gov/resources/advisories/fincen-advisory-fin-2010-a001) | High-volume DOP/USD exchanges inconsistent with customer profile | `def detect_peso_exchange(txns, acct): fx_vol = sum(t.amount for t in txns if t.currency_pair in ['DOP/USD','USD/DOP']); return fx_vol > acct.expected_fx_volume * 3` | `def feat_fx_volume_vs_expected(txns, acct): return actual_fx_vol / expected_fx_vol` |
| 20 | **Commingling Personal & Business** | [AML Watcher](https://amlwatcher.com/blog/how-commingling-blur-the-lines-between-legitimate-illegal-wealth/), [FFIEC Appendix F](https://bsaaml.ffiec.gov/manual/Appendices/07) | Personal account used for business or business account for personal | `def detect_commingling(personal_txns, business_txns, owner_id): cross_transfers = [t for t in personal_txns+business_txns if t.counterparty_owner==owner_id]; return len(cross_transfers) >= 5` | `def feat_personal_business_transfer_count(txns, owner_accounts): return count_transfers_between_own_accounts` |
| 21 | **Cash-Intensive Business Inflated Revenue** | [FFIEC CIB](https://bsaaml.ffiec.gov/manual/RisksAssociatedWithMoneyLaunderingAndTerroristFinancing/29) | Cash deposits exceed peer group norm for business type | `def detect_inflated_cash(acct, deposits, peer_avg): cash = sum(d.amount for d in deposits if d.type=='CASH'); return cash > peer_avg * 2` | `def feat_cash_deposit_peer_percentile(acct, deposits, peer_group): return percentile_rank(cash_total, peer_group_values)` |
| 22 | **Shell Business (No Expenses)** | [Financial Crime Academy](https://financialcrimeacademy.org/red-flags-in-high-risk-industries/) | Business account with deposits but no typical operating expenses | `def detect_shell_business(txns, min_days=90): credits = sum(t.amount for t in txns if t.type=='CREDIT'); op_expenses = sum(t.amount for t in txns if t.category in ['RENT','UTILITIES','SUPPLIES']); return credits > 0 and op_expenses < credits * 0.05` | `def feat_expense_to_revenue_ratio(txns): return operating_expenses / total_credits` |
| 23 | **Bulk Cash Smuggling (DR-Specific)** | [US State Dept](https://2009-2017.state.gov/j/inl/rls/nrcrpt/2016/vol2/253396.htm) | Large cash deposits from couriers with no clear source of funds, often followed by remittance | `def detect_bulk_cash_courier(txns, acct): large_cash = [t for t in txns if t.type=='CASH_DEP' and t.amount>=5000]; followed_by_remittance = any(is_remittance_within(t, txns, hours=48) for t in large_cash); return followed_by_remittance and not acct.has_documented_source` | `def feat_cash_deposit_to_remittance_ratio(txns): return cash_followed_by_wire / total_cash_deposits` |
| 24 | **Trade-Based Money Laundering** | [FATF](https://www.fatf-gafi.org/en/publications/Mutualevaluations/Mer-dominican-republic-2018.html), [InSight Crime](https://insightcrime.org/news/brief/dominican-republic-massive-money-laundering/) | Over/under invoicing, misrepresentation of goods/services in trade finance | `def detect_tbml(invoices, market_prices): return any(abs(inv.unit_price - market_prices[inv.item]) / market_prices[inv.item] > 0.5 for inv in invoices)` | `def feat_invoice_price_deviation(invoices, market_prices): return max_pct_deviation_from_market` |
| 25 | **Velocity Spike (Any Channel)** | [Sumsub](https://sumsub.com/blog/transaction-monitoring/), [Mozn](https://www.mozn.ai/blog/aml-transaction-monitoring-rules) | Transaction count or volume dramatically exceeds historical baseline | `def detect_velocity_spike(txns, baseline_window=90, current_window=7, multiplier=3): baseline_rate = count_txns(baseline_window) / baseline_window * current_window; current_rate = count_txns(current_window); return current_rate > baseline_rate * multiplier` | `def feat_velocity_ratio_7d_vs_90d(txns): return txn_count_7d / (txn_count_90d / 13)` |
| 26 | **PEP Transaction Monitoring** | [Wolfsberg](https://wolfsberg-group.org/resources/168/), [FATF R.12](https://www.fatf-gafi.org/en/countries/black-and-grey-lists.html) | Enhanced monitoring of politically exposed persons and their associates | `def detect_pep_unusual_activity(txn, acct): return acct.is_pep and (txn.amount > acct.expected_monthly * 0.5 or txn.dest_country in high_risk_list)` | `def feat_pep_activity_vs_declared_income(txns, acct): return total_volume / declared_annual_income` |
| 27 | **Circular Fund Flow** | [Linkurious](https://linkurious.com/blog/anti-money-laundering-use-cases-graph-analytics/), [Oracle](https://www.oracle.com/financial-services/aml-financial-crime-compliance/graph-analytics-powers-the-game/) | Funds leaving an account and returning via different path | `def detect_circular_flow(graph, acct, max_hops=5): paths = find_cycles(graph, acct, max_hops); return len(paths) > 0` | `def feat_circular_flow_count(graph, acct): return count_cycles_involving_account` |
| 28 | **Shared Identity Attributes** | [Linkurious](https://linkurious.com/blog/anti-money-laundering-use-cases-graph-analytics/), [McKinsey](https://www.mckinsey.com/industries/financial-services/our-insights/banking-matters/network-analytics-and-the-fight-against-money-laundering) | Multiple accounts sharing phone, address, email, or IP | `def detect_shared_identity(acct, all_accounts): shared = [a for a in all_accounts if a.phone==acct.phone or a.address==acct.address and a.id!=acct.id]; return len(shared) >= 3` | `def feat_shared_attribute_count(acct): return count_accounts_sharing_any_PII` |
| 29 | **Cross-Channel Layering** | [Financial Integrity Institute](https://finintegrity.org/from-cash-to-clicks-aml-challenges-typologies-for-digital-payments/) | Funds moved across multiple channels (cash->P2P->wire) rapidly | `def detect_cross_channel_layering(txns, hours=48): channels_used = set(t.channel for t in txns if within_hours(t, txns[0], hours)); return len(channels_used) >= 3` | `def feat_channel_entropy_48h(txns): return shannon_entropy(channel_distribution_48h)` |
| 30 | **Off-Hours Transaction Pattern** | [Sanctions.io](https://www.sanctions.io/blog/anti-money-laundering-aml-transaction-monitoring-rules-and-best-practices) | Concentrated activity between midnight-5 AM | `def detect_off_hours_pattern(txns, window_days=30): off_hours = [t for t in txns if t.hour >= 0 and t.hour <= 5]; return len(off_hours) / len(txns) > 0.3` | `def feat_off_hours_ratio(txns): return off_hours_count / total_count` |
| 31 | **New Account High Activity** | [Nacha](https://www.nacha.org/rules/risk-management-topics-fraud-monitoring-phase-1) | Account < 30 days old with high transaction volume or value | `def detect_new_account_burst(acct, txns): return acct.age_days < 30 and (sum(t.amount for t in txns) > 50000 or len(txns) > 20)` | `def feat_activity_per_account_age_day(acct, txns): return total_volume / max(account_age_days, 1)` |
| 32 | **Denomination Anomaly** | [FFIEC Appendix F](https://bsaaml.ffiec.gov/manual/Appendices/07) | Large cash deposits in predominantly small denominations | `def detect_denomination_anomaly(cash_deposit): return cash_deposit.amount > 5000 and cash_deposit.small_bill_pct > 0.8` | `def feat_small_denomination_pct(cash_deposits): return sum_small_bills / sum_total_bills` |
| 33 | **Real Estate ML (DR-Specific)** | [US State Dept](https://2009-2017.state.gov/j/inl/rls/nrcrpt/2016/vol2/253396.htm), [FATF DR](https://www.fatf-gafi.org/en/publications/Mutualevaluations/Mer-dominican-republic-2018.html) | Large payments to real estate/construction entities in DR, especially if cash-funded | `def detect_real_estate_ml(txns): re_payments = [t for t in txns if t.beneficiary_category=='REAL_ESTATE']; cash_funded = sum(t.amount for t in txns if t.type=='CASH_DEP') > sum(t.amount for t in re_payments) * 0.5; return cash_funded and sum(t.amount for t in re_payments) > 50000` | `def feat_real_estate_payment_to_income_ratio(txns, acct): return re_payments_total / declared_income` |
| 34 | **Casino/Gaming Transactions (DR-Specific)** | [FATF DR](https://www.fatf-gafi.org/en/publications/Mutualevaluations/Mer-dominican-republic-2018.html) | Frequent transactions with casinos disproportionate to customer profile | `def detect_casino_activity(txns, acct): casino_txns = [t for t in txns if t.merchant_category=='CASINO']; return sum(t.amount for t in casino_txns) > acct.monthly_income * 0.5` | `def feat_casino_txn_ratio(txns): return casino_volume / total_volume` |
| 35 | **Remittance Corridor Abuse (DR-US)** | [FinCEN Advisory](https://www.fincen.gov/resources/advisories/fincen-advisory-fin-2010-a001) | High-frequency or high-value remittances on US-DR corridor | `def detect_corridor_abuse(txns, corridor='US-DR', threshold=5000, count_threshold=10, window_days=30): corridor_txns = [t for t in txns if t.corridor==corridor]; return len(corridor_txns) > count_threshold or sum(t.amount for t in corridor_txns) > threshold * count_threshold` | `def feat_corridor_volume_percentile(txns, corridor, peer_group): return percentile_rank(corridor_volume, peer_volumes)` |
| 36 | **Vendor Kickback Pattern** | [FFIEC Appendix F](https://bsaaml.ffiec.gov/manual/Appendices/07) | Business pays vendor, then receives cash deposit of similar amount | `def detect_vendor_kickback(txns, days=7): vendor_payments = [t for t in txns if t.type=='VENDOR_PAY']; subsequent_cash = [t for t in txns if t.type=='CASH_DEP']; return any(abs(c.amount-v.amount)/v.amount < 0.1 and (c.date-v.date).days <= days for v in vendor_payments for c in subsequent_cash)` | `def feat_vendor_payment_cash_return_correlation(txns): return correlation(vendor_pay_amounts, subsequent_cash_amounts)` |
| 37 | **Payroll Timing Irregularity** | [Nacha Phase 2](https://www.nacha.org/rules/risk-management-topics-fraud-monitoring-phase-2) | Payroll disbursements not aligned with standard pay cycles | `def detect_payroll_irregularity(payroll_txns): intervals = [(t2.date-t1.date).days for t1,t2 in consecutive_pairs(payroll_txns)]; return std(intervals) > 5  # high variability in pay intervals` | `def feat_payroll_interval_cv(payroll_txns): return std(intervals) / mean(intervals)` |
| 38 | **Peer Group Deviation** | [Solytics](https://www.solytics-partners.com/resources/case-studies/peer-group-analysis-for-aml-transaction-monitoring), [FICO](https://www.fico.com/blogs/using-ai-and-machine-learning-improve-aml) | Customer activity significantly deviates from peer group norms | `def detect_peer_deviation(acct, peer_group, metric, threshold_std=3): peer_mean = mean(peer_group[metric]); peer_std = std(peer_group[metric]); return abs(acct[metric] - peer_mean) > threshold_std * peer_std` | `def feat_peer_zscore(acct, peer_group, metric): return (acct_value - peer_mean) / peer_std` |
| 39 | **Forged Credit Card Transactions (DR-Specific)** | [US State Dept](https://2009-2017.state.gov/j/inl/rls/nrcrpt/2016/vol2/253396.htm), [FATF DR](https://www.fatf-gafi.org/en/publications/Mutualevaluations/Mer-dominican-republic-2018.html) | Fraudulent credit card activity particularly prevalent in DR | `def detect_forged_card(txns): return any(t.fraud_score > 0.8 or t.chargeback_flag for t in txns if t.channel=='CARD')` | `def feat_chargeback_rate(txns): return chargeback_count / total_card_txn_count` |
| 40 | **Human Trafficking Financial Indicators** | [FinCEN Advisory](https://www.fincen.gov/resources/advisories/fincen-advisory-fin-2010-a001) | Multiple people sending funds to same individual, structured payments to hotels/transport, victim-age demographics | `def detect_trafficking_indicators(txns, acct): hotel_transport = [t for t in txns if t.mcc in HOTEL_TRANSPORT_MCCS]; multiple_senders = len(set(t.originator for t in txns if t.type=='CREDIT')) > 5; return multiple_senders and len(hotel_transport) > 3` | `def feat_hotel_transport_txn_ratio(txns): return hotel_transport_volume / total_volume` |

---

## Appendix A: DR-Specific Risk Considerations for System Design

### Priority Monitoring Scenarios for a Dominican Republic Retail Bank

1. **US-DR Remittance Corridor**: The most critical corridor. Monitor for structured remittances, bulk cash deposits followed by wires to the US, and reverse flows.
2. **Currency Exchange (DOP/USD)**: Casa de cambio-like activity through bank accounts. Monitor for high-volume peso-dollar conversions.
3. **Real Estate & Construction Payments**: Major laundering vehicle in DR. Flag large payments to construction/real estate entities funded by cash.
4. **Drug Trafficking Proceeds**: Fentanyl and cocaine transshipment creates large cash volumes. Monitor for denomination anomalies, structured deposits, and courier patterns.
5. **Human Trafficking Financial Flows**: Multiple senders to single recipient, hotel/transport payments, structured payments.
6. **PEP Monitoring**: DR corruption risk requires robust PEP screening and enhanced monitoring.
7. **Trade-Based ML**: DR shows rapid growth in TBML. Monitor trade finance for pricing anomalies.
8. **Informal Economy**: Large unbanked/underbanked population creates challenges in distinguishing legitimate cash-intensive activity from laundering.

### Recommended Threshold Adjustments for DR Context

| Standard Threshold | DR Adjustment | Rationale |
|---|---|---|
| $10,000 CTR threshold | Apply DOP equivalent; consider $5,000 for enhanced monitoring | DR Law 155-17 thresholds + higher cash economy risk |
| 90-day dormancy period | Consider 60 days | Faster-moving illicit activity in Caribbean |
| 200% velocity spike | Consider 150% for high-risk customers | Lower tolerance for behavioral deviation in high-risk jurisdiction |
| 3 branches for branch hopping | Consider 2 branches for structuring scenarios | Smaller branch network in DR |

---

## Appendix B: Key Source Reference Index

| # | Source | URL |
|---|---|---|
| 1 | FFIEC BSA/AML Examination Manual | https://bsaaml.ffiec.gov/manual |
| 2 | FFIEC Appendix F - Red Flags | https://bsaaml.ffiec.gov/manual/Appendices/07 |
| 3 | FFIEC Appendix S - Key Monitoring Components | https://bsaaml.ffiec.gov/manual/Appendices/20 |
| 4 | FFIEC - Cash-Intensive Businesses | https://bsaaml.ffiec.gov/manual/RisksAssociatedWithMoneyLaunderingAndTerroristFinancing/29 |
| 5 | FFIEC - ACH Transactions | https://bsaaml.ffiec.gov/manual/RisksAssociatedWithMoneyLaunderingAndTerroristFinancing/08 |
| 6 | FFIEC - Funds Transfers | https://bsaaml.ffiec.gov/manual/RisksAssociatedWithMoneyLaunderingAndTerroristFinancing/07 |
| 7 | FFIEC - Electronic Banking | https://bsaaml.ffiec.gov/manual/RisksAssociatedWithMoneyLaunderingAndTerroristFinancing/06 |
| 8 | FATF Dominican Republic MER 2018 | https://www.fatf-gafi.org/en/publications/Mutualevaluations/Mer-dominican-republic-2018.html |
| 9 | FATF Black and Grey Lists | https://www.fatf-gafi.org/en/countries/black-and-grey-lists.html |
| 10 | FinCEN Advisory FIN-2010-A001 | https://www.fincen.gov/resources/advisories/fincen-advisory-fin-2010-a001 |
| 11 | Wolfsberg Group - Effective Monitoring 2024 | https://wolfsberg-group.org/resources/168/ |
| 12 | Wolfsberg Group - Part II Innovation 2025 | https://wolfsberg-group.org/resources/202/ |
| 13 | Nacha - Fraud Monitoring Phase 1 | https://www.nacha.org/rules/risk-management-topics-fraud-monitoring-phase-1 |
| 14 | Nacha - Fraud Monitoring Phase 2 | https://www.nacha.org/rules/risk-management-topics-fraud-monitoring-phase-2 |
| 15 | Ondato - Structuring AML | https://ondato.com/blog/structuring-aml/ |
| 16 | Facctum - Structuring vs Smurfing | https://www.facctum.com/blog/structuring-vs-smurfing-in-aml-key-risks-detection-tactics |
| 17 | AMLTRIX - ATM Structuring | https://framework.amltrix.com/techniques/T0016.004-atm-structuring |
| 18 | AMLTRIX - P2P Transfers | https://framework.amltrix.com/techniques/T0134.001 |
| 19 | ComplyAdvantage - FX AML Risk | https://complyadvantage.com/insights/aml-risk-foreign-exchange/ |
| 20 | FinCrime Central - DR FX 2025 | https://fincrimecentral.com/aml-foreign-exchange-dominican-republic-2025/ |
| 21 | Linkurious - Graph Analytics AML | https://linkurious.com/blog/anti-money-laundering-use-cases-graph-analytics/ |
| 22 | McKinsey - Network Analytics AML | https://www.mckinsey.com/industries/financial-services/our-insights/banking-matters/network-analytics-and-the-fight-against-money-laundering |
| 23 | Oracle - Graph Analytics AML | https://www.oracle.com/financial-services/aml-financial-crime-compliance/graph-analytics-powers-the-game/ |
| 24 | Solytics - Peer Group Analysis | https://www.solytics-partners.com/resources/case-studies/peer-group-analysis-for-aml-transaction-monitoring |
| 25 | FICO - AI/ML for AML | https://www.fico.com/blogs/using-ai-and-machine-learning-improve-aml |
| 26 | Google Cloud - AML AI | https://cloud.google.com/anti-money-laundering-ai |
| 27 | IBM - AML Transaction Monitoring | https://www.ibm.com/think/topics/aml-transaction-monitoring |
| 28 | Sumsub - AML Monitoring Rules 2025 | https://sumsub.com/blog/aml-transaction-monitoring-rules-scenarios/ |
| 29 | Sumsub - Transaction Monitoring 2025 | https://sumsub.com/blog/transaction-monitoring/ |
| 30 | Sanctions.io - AML Rules & Best Practices | https://www.sanctions.io/blog/anti-money-laundering-aml-transaction-monitoring-rules-and-best-practices |
| 31 | Flagright - FATF Recommendations | https://www.flagright.com/post/understanding-fatf-recommendations-for-aml-compliance |
| 32 | Flagright - Effective Monitoring Rules | https://www.flagright.com/post/developing-effective-transaction-monitoring-rules |
| 33 | US State Dept - DR INCSR | https://2009-2017.state.gov/j/inl/rls/nrcrpt/2016/vol2/253396.htm |
| 34 | InSight Crime - DR Money Laundering | https://insightcrime.org/news/brief/dominican-republic-massive-money-laundering/ |
| 35 | Financial Crime Academy - Anomaly Detection | https://financialcrimeacademy.org/anomaly-detection-in-aml-data/ |
| 36 | Financial Crime Academy - FX ML | https://financialcrimeacademy.org/fx-money-laundering-and-money-remittance-a-potent-cocktail/ |
| 37 | AML Watcher - Cash-Intensive Businesses | https://amlwatcher.com/blog/anti-money-laundering-aml-guide-for-cash-intensive-businesses/ |
| 38 | AML Watcher - Commingling | https://amlwatcher.com/blog/how-commingling-blur-the-lines-between-legitimate-illegal-wealth/ |
| 39 | Abrigo - Check Fraud for AML | https://www.abrigo.com/blog/check-fraud-detection-tips-for-aml-professionals/ |
| 40 | Abrigo - P2P Fraud AML Trends | https://www.abrigo.com/blog/p2p-fraud-and-emerging-aml-trends/ |

---

*Document compiled: 2026-02-23*
*Research scope: AML transaction monitoring rules, anomaly detection features, small business monitoring, and FATF/Wolfsberg standards for a retail bank in the Dominican Republic*
