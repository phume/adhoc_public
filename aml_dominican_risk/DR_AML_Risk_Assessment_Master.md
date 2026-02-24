# Dominican Republic AML Risk Assessment — Master Document

**Date:** 2026-02-23
**Context:** Retail banking acquisition in the Dominican Republic — retail clients and small businesses
**Purpose:** Comprehensive AML risk assessment, rule-based monitoring design, and anomaly detection feature engineering

---

## Table of Contents

1. [Executive Summary](#1-executive-summary)
2. [Jurisdiction & Country Risk](#2-jurisdiction--country-risk)
3. [Narcotics, Human Trafficking & Illicit Finance](#3-narcotics-human-trafficking--illicit-finance)
4. [Rule-Based Transaction Monitoring by Channel](#4-rule-based-transaction-monitoring-by-channel)
5. [Anomaly Detection Feature Engineering](#5-anomaly-detection-feature-engineering)
6. [Small Business Specific Monitoring](#6-small-business-specific-monitoring)
7. [FATF & Wolfsberg Group Standards](#7-fatf--wolfsberg-group-standards)
8. [Consolidated Red Flag & Typology Table](#8-consolidated-red-flag--typology-table)
9. [Risk Assessment Matrix](#9-risk-assessment-matrix)
10. [Reference Documents](#10-reference-documents)

---

## 1. Executive Summary

The Dominican Republic presents a **high-risk AML environment** for retail banking. Key risk drivers:

- **Major Drug Transit Country** (US Presidential Determination FY2026) — 120+ tons of cocaine transit annually
- **Major Money Laundering Country** (INCSR Vol II) — bulk cash, remittances, real estate, casinos
- **$10.8B annual remittance corridor** — 80%+ from US, primary channel for illicit fund flows
- **54.7% informal employment** — cash-dominant economy, large unbanked population
- **Fentanyl distribution nexus** — Dominican nationals increasingly prosecuted in US Northeast
- **Human trafficking** — Tier 2 TIP rating; labor exploitation of Haitian migrants
- **TBML growth** — FinCEN identified DR as fastest-growing TBML origin country
- **FATF supervisory weakness** — IO.3 (supervisory oversight) rated "Low" in 2018 MER
- **Basel AML Index: 4.96/10** (medium risk, improved from 6.74 in 2016)
- **CPI: 37/100** — below Americas regional average of 42

### Key OFAC-Designated Entities (DR-Connected)
| Name | Basis | Year |
|------|-------|------|
| Cesar Emilio Peralta / Peralta DTO | Kingpin Act — cocaine/opioid trafficking | 2019 |
| Jose Calderon Rijo "La Arana" | E.O. 14059 — major drug trafficking | 2022 |
| Felix Ramon Bautista Rosario (Senator) | Global Magnitsky — corruption/bribery | 2018 |

---

## 2. Jurisdiction & Country Risk

> **Full reference:** [reference/DR_AML_Country_Risk_Profile.md](reference/DR_AML_Country_Risk_Profile.md)

### 2.1 FATF/GAFILAT Status

- **NOT on FATF grey or black list** (Feb 2026)
- Member of **GAFILAT** (not CFATF)
- 2018 MER: 14 Compliant, 20 Largely Compliant, 5 Partially Compliant, 1 Non-Compliant
- **Zero "High" effectiveness ratings** — supervisory oversight rated **Low**

**Ref:** [FATF MER 2018](https://www.fatf-gafi.org/en/publications/Mutualevaluations/Mer-dominican-republic-2018.html)

### 2.2 Legal Framework

- **Law 155-17 (2017)**: Primary AML/CFT statute — 30+ predicate offenses, CTR at $10,000, STR obligations
- **UAF** (Unidad de Analisis Financiero): Financial Intelligence Unit under Ministry of Finance
- Covers FIs, DNFBPs (real estate brokers, lawyers, notaries, accountants)

**Ref:** [National Law Review](https://natlawreview.com/article/dominican-republic-s-new-anti-money-laundering-and-terrorist-financing-act)

### 2.3 Key Vulnerability Profile

| Vulnerability | Severity | Details |
|---|---|---|
| Cash-intensive economy | Very High | Cash dominant outside major cities; bulk cash smuggling is primary illicit fund movement method |
| Informal economy | Very High | 54.7% informal employment; 34% informal GDP; large unbanked population |
| US-DR remittance corridor | High | $10.8B/year; 80%+ from US; wire transfers are primary illicit fund channel |
| Drug transit (cocaine) | Critical | 120+ tons/year; maritime routes from Colombia/Venezuela; Port of Caucedo to Europe |
| Fentanyl distribution | High | Growing trend; Dominican nationals as distributors in US Northeast |
| Free trade zones (TBML) | High | Gold laundering, over/under invoicing; fastest-growing TBML origin per FinCEN |
| Real estate sector | High | State Dept identifies as laundering vehicle; cash purchases, tokenization risk |
| Casino/gaming | High | 44 casinos; historically weak AML controls |
| Human trafficking | Moderate-High | Tier 2 TIP; 100K+ stateless persons; Haitian migrant exploitation |
| Corruption | High | CPI 37/100; judiciary and law enforcement corruption; DEA office shut down Feb 2026 |
| Correspondent banking | Moderate | Regional de-risking pressure; 21/23 Caribbean banks lost CBRs |

---

## 3. Narcotics, Human Trafficking & Illicit Finance

> **Full reference:** [reference/DR_Narcotics_Trafficking_AML_Research.md](reference/DR_Narcotics_Trafficking_AML_Research.md)

### 3.1 Drug Trafficking Routes

**Cocaine:**
- ~120 tons transit annually; ~3 go-fast boats/week from Venezuela (700kg-1 ton each)
- Port of Caucedo: container shipments to Antwerp, Belgium
- Dominican DTOs buy cocaine in Venezuela, take control upon arrival
- **Ref:** [InSight Crime](https://insightcrime.org/investigations/dominican-republic-venezuela-cocaine-across-caribbean/)

**Fentanyl:**
- 6+ major DEA prosecutions of Dominican nationals in 2024-2025
- Distribution hubs in Bronx NY, Massachusetts, Connecticut, Vermont
- FinCEN SARs link DR-based subjects to online pharmacies selling counterfeit opioid pills
- **Ref:** [DEA Press Releases 2024-2025](https://www.dea.gov/press-releases)

**Mexican Cartel Nexus:**
- Sinaloa Cartel: supplier-client relationship, NOT structured presence in DR (DEA confirmed Jul 2025)
- Sinaloa member arrested at Punta Cana airport (Feb 2025) — wanted for fentanyl trafficking
- **Ref:** [DR1.com](https://dr1.com/news/2025/07/10/dea-confirms-sinaloa-cartel-is-not-operating-in-the-dominican-republic/)

### 3.2 Money Laundering Typologies (DR-Specific)

| Typology | Key Case/Evidence | Scale |
|---|---|---|
| Nightclub laundering | Peralta DTO — 6 nightclubs in Santo Domingo (OFAC-designated) | $260M+ over 3 years |
| Shell companies + cashier checks | Velazquez-Cordero "El Pequeno" — shell corps, US bank cashier checks | $80M laundered |
| Remittance structuring | FinCEN GTOs — NY remitters, $750+ threshold imposed | $500M+/year from NY |
| Real estate integration | Cash purchases in Santo Domingo, Punta Cana, coastal resorts | Systemic |
| Currency exchange houses | Casas de cambio as primary laundering facilitator | Systemic |
| Casino laundering | Money laundering "common" around DR casinos | 44 casinos |
| FTZ gold laundering | Gold/jewelry through Free Trade Zones, pawnbroker networks | Growing |

### 3.3 Human Trafficking Financial Indicators

- DR is source, transit, and destination country
- 229 new investigations opened (2025 TIP Report)
- Largest stateless population in Western Hemisphere (100K+)
- 21% of Haitian construction workers reported forced labor
- Financial indicators: multiple senders to single account, hotel/transport payments, structured payroll
- **Ref:** [2025 TIP Report](https://www.state.gov/reports/2025-trafficking-in-persons-report/dominican-republic/)

### 3.4 Recent Major Enforcement Actions

| Operation | Date | Scale | Outcome |
|---|---|---|---|
| Operation Panthera 7 | Jan 2025 | 9.5 tons cocaine at Port of Caucedo | 15 arrested; largest DR seizure in history |
| Peralta DTO ("El Abusador") | 2019-ongoing | Multi-ton cocaine; $260M+ laundered | Guilty plea; facing life |
| Operation Falcon | Sep 2021 | 80+ raids; cocaine Colombia→DR→US/Europe | 27+ arrested; $4.9M seized |
| Velazquez-Cordero | 2020-2022 | $80M shell company laundering | 78 months federal prison |
| DEA Santo Domingo closure | Feb 2026 | Agent corruption (visa fraud scheme) | Office shuttered |

**Drug seizure trend:** 30+ tons in 2024 (5x increase since 2019); 18.4 tons in first 7 months of 2025.

---

## 4. Rule-Based Transaction Monitoring by Channel

> **Full reference:** [reference/AML_Transaction_Monitoring_Research.md](reference/AML_Transaction_Monitoring_Research.md)

### 4.1 Cash (Teller Deposits/Withdrawals) — 12 Rules

| Rule ID | Rule Name | Logic | Lookback |
|---|---|---|---|
| CASH-001 | Single Large Cash Deposit | >= $10,000 | Real-time |
| CASH-002 | Aggregate Cash Structuring | Multiple deposits < $10K, aggregate >= $10K, same account | 1 day |
| CASH-003 | Just-Below-Threshold | Any deposit $7,000-$9,999 | Real-time |
| CASH-004 | Multi-Day Structuring | Cumulative >= $20K, each < $10K | 5 days |
| CASH-005 | Smurfing Multi-Account | Deposits across 3+ own accounts, aggregate >= $10K | 1 day |
| CASH-006 | Smurfing Multi-Person | 3+ depositors to same account, aggregate >= $10K | 3 days |
| CASH-007 | Cash-In/Cash-Out Rapid | Deposit then withdrawal >= 80% within 24-48h | 48 hours |
| CASH-008 | Cash Deposit then Wire | $5K+ cash deposit followed by international wire | 72 hours |
| CASH-009 | Cash Deposit Velocity Spike | Frequency exceeds 200% of 90-day rolling average | 7d vs 90d |
| CASH-010 | Round Amount Cash | Repeated round amounts ($5K, $9K, $9.5K) | 30 days |
| CASH-011 | Branch Hopping | Cash deposits at 3+ branches | 5 days |
| CASH-012 | Denomination Anomaly | Unusual denomination mix (all small bills for large amount) | Real-time |

### 4.2 ATM/ABM — 10 Rules

| Rule ID | Rule Name | Logic | Lookback |
|---|---|---|---|
| ATM-001 | High-Value ATM Withdrawal | Single withdrawal near daily limit | Real-time |
| ATM-002 | ATM Withdrawal Velocity | 5+ ATM txns within 10 minutes | Real-time |
| ATM-003 | Daily Limit Maximization | Consistently hitting daily limit | 7 consecutive days |
| ATM-004 | Multi-ATM Same Day | 5+ different ATMs in single day | 1 day |
| ATM-005 | ATM Deposit Structuring | Multiple ATM deposits < $10K, aggregate >= $10K | 1 day |
| ATM-006 | Impossible Travel | Locations > 100km apart within 2-4 hours | Real-time |
| ATM-007 | Cross-Border ATM | Foreign country ATM inconsistent with profile | Real-time |
| ATM-008 | After-Hours Pattern | Large ATM txns between midnight-5 AM | 30 days |
| ATM-009 | ATM-to-Wire Sequence | ATM deposits followed by wire transfer | 48 hours |
| ATM-010 | Dormant Account ATM | ATM activity after 90+ day dormancy | Real-time |

### 4.3 Cheque — 10 Rules

| Rule ID | Rule Name | Logic | Lookback |
|---|---|---|---|
| CHQ-001 | Cheque Kiting Cross-Bank | Cheques between accounts at different banks, no business purpose | 30 days |
| CHQ-002 | Cheque Kiting Velocity | 5+ cheques from different banks, insufficient funds | 5 days |
| CHQ-003 | RDC Duplicate | Same cheque deposited via RDC and physically | Real-time |
| CHQ-004 | RDC Volume Spike | RDC volume > 200% of baseline | 30 days |
| CHQ-005 | Third-Party Cheques | Cheques payable to others deposited into own account | 30 days |
| CHQ-006 | Large Cheque Immediate Withdrawal | Large deposit + withdrawal before clearing | 48 hours |
| CHQ-007 | Sequential Serial Numbers | Money orders/cashier cheques with sequential numbers | 30 days |
| CHQ-008 | Cheque-to-Cash Ratio | > 80% of cheque deposits converted to cash | 30 days |
| CHQ-009 | Altered/Washed Cheque | Flagged for physical alterations | Real-time |
| CHQ-010 | Counter Cheque Abuse | Excessive counter cheques for large transactions | 30 days |

### 4.4 Wire Transfers — 13 Rules

| Rule ID | Rule Name | Logic | Lookback |
|---|---|---|---|
| WIRE-001 | Large International Wire | >= $50K (low-risk) or >= $10K (high-risk) | Real-time |
| WIRE-002 | High-Risk Corridor | Wire to/from FATF high-risk jurisdiction | Real-time |
| WIRE-003 | Wire Structuring | Multiple wires < threshold, aggregate >= threshold | 5 days |
| WIRE-004 | Rapid Wire Velocity | 5+ wires in 24-72h or rapid new beneficiaries | 72 hours |
| WIRE-005 | Round-Amount Wires | Exact round amounts, no commercial basis | 30 days |
| WIRE-006 | Layering Pass-Through | Incoming wire → immediate outgoing wire similar amount | 48 hours |
| WIRE-007 | Wire to Shell Company | Wire to secrecy jurisdiction entity, no commercial relationship | Real-time |
| WIRE-008 | DR-US Corridor Wire | US-DR corridor volume exceeds 200% baseline | 30 days |
| WIRE-009 | Fan-Out | Single incoming split into multiple outgoing | 48 hours |
| WIRE-010 | Fan-In | Multiple incoming consolidated into single outgoing | 72 hours |
| WIRE-011 | Wire + Cash Combo | Cash deposit followed by international wire | 48 hours |
| WIRE-012 | Incomplete Originator Info | Missing originator/beneficiary (Travel Rule violation) | Real-time |
| WIRE-013 | Dormant-to-Wire | Dormant > 90 days, suddenly wire activity | Real-time |

### 4.5 P2P / Digital Payments — 9 Rules

| Rule ID | Rule Name | Logic | Lookback |
|---|---|---|---|
| P2P-001 | Rapid Disbursement | 10+ P2P payments to unique recipients in < 24h | 24 hours |
| P2P-002 | P2P Structuring | Multiple P2P to same recipient, aggregate >= threshold | 5 days |
| P2P-003 | P2P Collection | 10+ unique senders, aggregate > $5K | 7 days |
| P2P-004 | P2P-to-Wire Chain | P2P receipts → wire transfer of similar amount | 48 hours |
| P2P-005 | New-Account P2P Burst | Account < 30 days with high-volume P2P | 30 days |
| P2P-006 | P2P Round Amounts | Repeated exact round P2P amounts | 30 days |
| P2P-007 | Cross-Channel Layering | P2P receipt → cash withdrawal → different P2P | 48 hours |
| P2P-008 | P2P Velocity vs Baseline | Count/volume exceeds 300% of 90-day average | 7d vs 90d |
| P2P-009 | Late-Night P2P | Concentrated between midnight-5 AM | 30 days |

### 4.6 ACH/EFT — 8 Rules

| Rule ID | Rule Name | Logic | Lookback |
|---|---|---|---|
| ACH-001 | Unauthorized Debit | ACH debit with no authorization history | Real-time |
| ACH-002 | High-Velocity Credits | 5+ ACH credits from unrelated originators | 3 days |
| ACH-003 | Multiple Unrelated Payroll | Multiple payroll credits from different employers | 30 days |
| ACH-004 | New/Dormant + High ACH | New/dormant account receiving high-value ACH | Real-time |
| ACH-005 | ACH Credit then Withdrawal | ACH credit → immediate cash/wire >= 80% | 48 hours |
| ACH-006 | Return Rate Anomaly | ACH return rate > 15% | 30 days |
| ACH-007 | SEC Code Mismatch | SEC code inconsistent with account type | Real-time |
| ACH-008 | Payroll Velocity Spike | Payroll count exceeds 200% of 3-month average | Monthly vs 90d |

### 4.7 Foreign Exchange — 9 Rules

| Rule ID | Rule Name | Logic | Lookback |
|---|---|---|---|
| FX-001 | Large FX Transaction | >= $10,000 equivalent | Real-time |
| FX-002 | FX Structuring | Multiple FX < threshold, aggregate >= threshold | 5 days |
| FX-003 | Unusual Currency Pair | Non-standard pair for customer's business | Real-time |
| FX-004 | Peso Exchange High Volume | DOP/USD volume inconsistent with profile | 30 days |
| FX-005 | Round Trip FX | A→B→A with no economic purpose | 30 days |
| FX-006 | FX + Wire Combo | FX conversion → international wire in converted currency | 48 hours |
| FX-007 | Off-Market Rate | Customer accepts > 5% spread from market rate | Real-time |
| FX-008 | Multiple Casa de Cambio | FX at multiple exchange houses | 30 days |
| FX-009 | Seasonal FX Anomaly | Volume deviates from seasonal expectations | 12-month comparison |

**Total: 71 rules across 7 channels**

---

## 5. Anomaly Detection Feature Engineering

> **Full reference:** [reference/AML_Transaction_Monitoring_Research.md](reference/AML_Transaction_Monitoring_Research.md) — Section 3

### 5.1 Customer Behavior Features (20 features)

| Feature | Description | Computation |
|---|---|---|
| `txn_count_1d/7d/30d` | Transaction count over rolling windows | COUNT(txns) in window |
| `txn_amount_sum_1d/7d/30d` | Sum of amounts over rolling windows | SUM(amount) in window |
| `txn_amount_avg_30d` | Average transaction amount | MEAN(amount) over 30d |
| `txn_amount_std_30d` | Standard deviation of amounts | STD(amount) over 30d |
| `txn_amount_zscore` | Z-score of current txn vs 90d history | (current - mean_90d) / std_90d |
| `txn_velocity_ratio` | 7d velocity vs 90d average | count_7d / (count_90d / 13) |
| `avg_time_between_txns` | Mean time gap between txns | MEAN(time_diff) |
| `time_since_last_txn` | Hours since last transaction | NOW() - last_txn |
| `is_off_hours` | Transaction outside 8pm-6am | Boolean |
| `weekend_txn_ratio` | Weekend proportion | weekend_count / total_count |
| `channel_entropy` | Diversity of channel usage | Shannon entropy |
| `channel_shift_flag` | Sudden channel change | Boolean |
| `cash_to_total_ratio` | Cash proportion of total | cash_amount / total_amount |
| `debit_credit_ratio` | Debit vs credit ratio | sum_debits / sum_credits |
| `round_amount_ratio` | Round amount proportion | round_count / total_count |
| `just_below_threshold_count` | Txns at 70-99% of threshold | COUNT in range |
| `unique_counterparties_7d/30d` | Unique beneficiaries/originators | COUNT DISTINCT |
| `new_counterparty_ratio` | New vs existing counterparties | new / total |

### 5.2 Network/Graph Features (15 features)

| Feature | Description |
|---|---|
| `shared_address_count` | Accounts sharing same address |
| `shared_phone_count` | Accounts sharing same phone |
| `shared_email_count` | Accounts sharing same email |
| `shared_ip_count` | Accounts sharing same IP |
| `shared_beneficiary_count` | Accounts sending to same beneficiary |
| `common_beneficiary_overlap` | Jaccard similarity with flagged accounts |
| `in_degree_centrality` | Unique incoming fund sources |
| `out_degree_centrality` | Unique outgoing fund destinations |
| `betweenness_centrality` | Shortest-path frequency measure |
| `community_cluster_id` | Community detection cluster |
| `fund_flow_circularity` | Funds returning within N hops |
| `fan_in_ratio` | in_degree / out_degree |
| `fan_out_ratio` | out_degree / in_degree |
| `layering_depth` | Max chain length from account |
| `shell_company_score` | Shell entity likelihood composite |

### 5.3 Geographic Features (20 features)

| Feature | Description |
|---|---|
| `high_risk_jurisdiction_flag` | FATF-listed country involved |
| `high_risk_jurisdiction_count_30d` | Count of high-risk country txns |
| `cross_border_ratio` | Cross-border / domestic ratio |
| `unique_countries_30d` | Distinct countries in txns |
| `atm_location_entropy` | ATM location diversity |
| `atm_max_distance_km` | Max ATM distance in a day |
| `impossible_travel_flag` | Geographically impossible locations |
| `ip_geolocation_mismatch` | IP vs registered address mismatch |
| `ip_country_changes_30d` | Distinct IP countries |
| `dr_us_corridor_volume` | DR-US corridor transaction volume |
| `remittance_corridor_ratio` | Corridor txns / total |
| `branch_location_anomaly` | Unusual branch for customer |
| `nationality_txn_geography_mismatch` | % of transactions in countries other than residency or nationality |
| `mexico_txn_ratio_30d` | Mexico POS/ATM transactions / total (Sinaloa nexus indicator) |
| `us_northeast_remittance_ratio` | Remittances from NJ/NY/MA/CT / total incoming |
| `nightclub_mcc_spend_ratio_30d` | MCC 5813 (bars), 7911 (entertainment), 5812 (restaurants) spend / total |
| `late_night_txn_ratio` | Transactions 11PM–5AM / total (lifestyle indicator) |
| `tourist_zone_txn_ratio` | Transactions in Punta Cana/Bávaro/Samaná/La Romana for non-tourism clients |
| `transit_route_country_count_30d` | Distinct countries on known drug transit routes in 30 days |
| `geo_lifestyle_inconsistency_score` | Composite: declared income vs. geo-spending pattern mismatch |

### 5.4 Account Features (17 features)

| Feature | Description |
|---|---|
| `account_age_days` | Days since account opened |
| `is_new_account` | < 90 days old |
| `is_dormant_reactivated` | > 90 days inactive, recently active |
| `product_count` | Number of products held |
| `product_mix_risk_score` | Risk based on product combination |
| `expected_monthly_volume` | From CDD/KYC profile |
| `actual_vs_expected_ratio` | Actual / expected activity |
| `balance_avg_30d` | Mean daily balance |
| `balance_volatility` | STD / MEAN of daily balance |
| `balance_spike_flag` | Balance > 500% of 90d avg |
| `credit_utilization` | Outstanding / limit |
| `overdraft_frequency_30d` | Overdraft events |
| `pep_flag` | Politically Exposed Person |
| `sanctions_proximity_score` | Fuzzy match to sanctions lists |
| `adverse_media_flag` | Negative news association |
| `risk_rating` | Customer risk rating |
| `sar_history_count` | Prior SARs filed |

### 5.5 Temporal Features (14 features)

| Feature | Description |
|---|---|
| `day_of_week` | 0=Monday to 6=Sunday |
| `is_weekend` | Saturday/Sunday flag |
| `is_holiday` | DR public holiday flag |
| `hour_of_day` | 0-23 |
| `time_of_day_bucket` | Morning/afternoon/evening/night |
| `month_of_year` | 1-12 for seasonality |
| `is_month_end` | Last 3 business days |
| `is_tax_season` | Tax filing period |
| `days_since_account_open` | Days from opening |
| `burst_score` | 1h count / avg hourly 90d |
| `inter_transaction_time_cv` | CV of time between txns |
| `activity_trend_slope` | Weekly volume slope (12 weeks) |
| `seasonal_deviation` | Current month vs same month prior year |
| `recency_of_first_txn` | Days since first-ever txn |

### 5.6 Peer Group Features (10 features)

| Feature | Description |
|---|---|
| `peer_group_id` | Assigned peer group |
| `peer_txn_volume_percentile` | Volume rank within peers |
| `peer_txn_count_percentile` | Count rank within peers |
| `peer_cash_ratio_deviation` | Cash ratio vs peer median |
| `peer_avg_txn_deviation` | Avg txn size vs peers |
| `peer_channel_mix_distance` | Channel distribution distance |
| `peer_wire_ratio_deviation` | Wire proportion vs peers |
| `peer_counterparty_count_deviation` | Counterparty count vs peers |
| `peer_dormancy_deviation` | Dormancy pattern vs peers |
| `archetype_misalignment_score` | Behavioral archetype mismatch |

**Total: 96 features across 6 categories**

---

## 6. Small Business Specific Monitoring

> **Full reference:** [reference/AML_Transaction_Monitoring_Research.md](reference/AML_Transaction_Monitoring_Research.md) — Section 4

### Cash-Intensive Business Types (DR Context)
Restaurants, bars, nightclubs, retail/convenience stores, gas stations, car washes, laundromats, parking garages, colmados, street vendors, market sellers

### 25 Small Business Rules

**Cash-Intensive (5):** Peer comparison, consistency check, revenue-location mismatch, cash-to-revenue ratio, seasonal anomaly

**Revenue Consistency (5):** Revenue spike (>300% of 6-month avg), tax filing mismatch, employee-revenue ratio, weekend/holiday deposits when closed, no expense pattern (shell business)

**Payroll Anomalies (5):** Ghost employees, related-party payroll, amount anomaly, timing irregularity, new payroll recipient spike

**Vendor Payments (5):** New vendor spike, high-risk jurisdiction vendor, round amount vendor payments, vendor concentration (>80% to single vendor), vendor kickback pattern

**Commingling (5):** Personal-to-business transfers, business account personal expenses, cash extraction pattern, multi-business intermingling, personal account as unregistered business

---

## 7. FATF & Wolfsberg Group Standards

> **Full reference:** [reference/AML_Transaction_Monitoring_Research.md](reference/AML_Transaction_Monitoring_Research.md) — Section 5

### FATF: 14 Recommended Monitoring Scenario Categories
Structuring, unusual size, rapid movement, high-risk jurisdiction, PEP, unusual business activity, complex patterns, virtual asset structuring, TBML, correspondent banking, wire Travel Rule, cash-intensive business, terrorism financing, proliferation financing

### Wolfsberg (2024-2025): Key Principles
- Risk-based monitoring calibrated to institution
- MSA (Monitoring for Suspicious Activity) broader than just TM
- Peer group analytics and spending pattern analysis
- Quality over quantity in alerts
- AI/ML integration alongside traditional rules
- Explainability requirement for ML models
- Continuous calibration and back-testing

### DR-Specific Threshold Adjustments

| Standard | DR Adjustment | Rationale |
|---|---|---|
| $10,000 CTR | Apply DOP equivalent; $5,000 enhanced monitoring | Law 155-17 + higher cash economy risk |
| 90-day dormancy | Consider 60 days | Faster-moving illicit activity in Caribbean |
| 200% velocity spike | Consider 150% for high-risk customers | Lower tolerance in high-risk jurisdiction |
| 3 branches for hopping | Consider 2 branches | Smaller branch network in DR |

---

## 8. Consolidated Red Flag & Typology Table

This table consolidates all identified red flags from all three reference documents. Each entry includes the typology, source reference, description, a potential rule-based Python function, and a potential anomaly detection feature function.

| # | Red Flag / AML Risk Typology | Reference Source | Description | Rule-Based Python Function | Anomaly Detection Feature |
|---|---|---|---|---|---|
| 1 | **Cash Structuring (Single Account)** | [FFIEC Appendix F](https://bsaaml.ffiec.gov/manual/Appendices/07); [Ondato](https://ondato.com/blog/structuring-aml/) | Multiple cash deposits below $10K threshold aggregating above $10K within a day | `def detect_cash_structuring(txns, threshold=10000, window_days=1)` — Flag when sum >= threshold and all individual deposits < threshold | `feat_just_below_threshold_count(txns)` — Count of txns between 70-99% of threshold |
| 2 | **Smurfing (Multi-Person Deposits)** | [Facctum](https://www.facctum.com/blog/structuring-vs-smurfing-in-aml-key-risks-detection-tactics); [INCSR](https://www.state.gov/2025-international-narcotics-control-strategy-report) | 3+ different individuals depositing to same account, aggregate >= threshold | `def detect_smurfing(deposits, acct, threshold=10000, window_days=3)` — Flag when unique depositors >= 3 and aggregate >= threshold | `feat_unique_depositors_count(deposits, window=3d)` — Count of distinct depositor IDs |
| 3 | **Smurfing (Multi-Account)** | [Focal AI](https://www.getfocal.ai/blog/difference-between-smurfing-and-structuring) | Same customer deposits across 3+ own accounts, aggregate >= threshold | `def detect_multi_acct_smurfing(txns, customer_accts, threshold=10000)` — Aggregate across all customer accounts | `feat_cross_account_cash_aggregate(customer_accts)` — Sum of cash across all owned accounts |
| 4 | **Just-Below-Threshold Deposits** | [AMLTRIX](https://framework.amltrix.com/techniques/T0016.004-atm-structuring) | Repeated deposits at $7K-$9.9K range | `def detect_just_below(txns, low=7000, high=9999)` — Flag frequency of deposits in range | `feat_pct_deposits_in_threshold_band(txns)` — Ratio of deposits in 70-99% range |
| 5 | **Rapid Fund Movement (Pass-Through)** | [INCSR Vol 2](https://www.state.gov/wp-content/uploads/2025/01/2024-INCSR-Vol-2-Money-Laundering-Accessible-Version.pdf); [Sanctions.io](https://www.sanctions.io/blog/anti-money-laundering-aml-transaction-monitoring-rules-and-best-practices) | Funds deposited and moved out within 24-48h (80%+ of deposit) | `def detect_passthrough(txns, hours=48, pct=0.8)` — Flag when outflow >= 80% of inflow within window | `feat_avg_fund_holding_period(txns)` — Mean hours between deposit and withdrawal |
| 6 | **Cash-Then-Wire Sequence** | [FFIEC Funds Transfers](https://bsaaml.ffiec.gov/manual/RisksAssociatedWithMoneyLaunderingAndTerroristFinancing/07) | Large cash deposit followed by international wire of similar amount | `def detect_cash_then_wire(txns, hours=72, match_pct=0.8)` — Pair cash deposits with subsequent wires | `feat_cash_to_wire_time_gap(txns)` — Min hours between cash deposit and wire |
| 7 | **Branch Hopping** | [FFIEC Appendix F](https://bsaaml.ffiec.gov/manual/Appendices/07) | Cash deposits at 3+ different branches in short period | `def detect_branch_hopping(txns, min_branches=3, window_days=5)` — Count unique branch IDs | `feat_unique_branches_used(txns, window=5d)` — Count of distinct branches |
| 8 | **Denomination Anomaly** | [FFIEC Appendix F](https://bsaaml.ffiec.gov/manual/Appendices/07) | Large cash deposit in predominantly small denominations (drug proceeds indicator) | `def detect_denomination_anomaly(deposit, small_bill_pct_threshold=0.8)` — Flag when small bill % > 80% | `feat_small_denomination_pct(deposits)` — Ratio of small bill amounts |
| 9 | **Round Amount Transactions** | [Sumsub](https://sumsub.com/blog/aml-transaction-monitoring-rules-scenarios/) | Repeated transactions in exact round amounts with no commercial basis | `def detect_round_amounts(txns, round_unit=1000, min_count=3)` — Count round-amount txns | `feat_round_amount_ratio(txns)` — Round txns / total txns |
| 10 | **ATM Structuring** | [AMLTRIX](https://framework.amltrix.com/techniques/T0016.004-atm-structuring) | Multiple ATM deposits each < threshold, aggregate >= threshold | `def detect_atm_structuring(txns, threshold=10000)` — Aggregate ATM deposits within window | `feat_atm_deposit_aggregate_ratio(txns, threshold)` — ATM deposit sum / threshold |
| 11 | **ATM Impossible Travel** | [Feedzai](https://www.feedzai.com/blog/what-is-aml-transaction-monitoring/) | ATM transactions > 100km apart within 2-4 hours | `def detect_impossible_travel(txns, max_speed_kmh=500)` — Haversine distance / time | `feat_max_atm_velocity_kmh(txns)` — Max km/h between consecutive ATM txns |
| 12 | **ATM Daily Limit Maximization** | [IBM](https://www.ibm.com/think/topics/aml-transaction-monitoring) | Consistently hitting daily ATM withdrawal limit | `def detect_limit_max(txns, days=7, pct=0.9)` — Flag hitting 90%+ of limit for N consecutive days | `feat_atm_daily_limit_utilization(txns)` — Withdrawal / daily limit ratio |
| 13 | **Cheque Kiting** | [Tookitaki](https://www.tookitaki.com/glossary/check-fraud); [Abrigo](https://www.abrigo.com/blog/check-fraud-detection-tips-for-aml-professionals/) | Cheques drawn between accounts at different banks exploiting float time | `def detect_cheque_kiting(txns, accts)` — Detect circular cheque patterns | `feat_cheque_deposit_velocity(txns)` — Cheque deposits per week |
| 14 | **RDC Duplicate Deposit** | [TechTarget](https://www.techtarget.com/searchcio/tip/How-AML-compliance-applies-to-remote-deposit-capture) | Same cheque deposited via RDC and at branch | `def detect_rdc_duplicate(rdc_deposits, branch_deposits)` — Match cheque images | `feat_rdc_to_branch_deposit_ratio(txns)` — RDC count / branch count |
| 15 | **Third-Party Cheque Deposits** | [FFIEC Electronic Banking](https://bsaaml.ffiec.gov/manual/RisksAssociatedWithMoneyLaunderingAndTerroristFinancing/06) | Cheques payable to others deposited into own account | `def detect_third_party_cheque(txns)` — Flag payee != account holder | `feat_third_party_cheque_pct(txns)` — Third-party / total cheque ratio |
| 16 | **Wire to High-Risk Jurisdiction** | [FATF Black/Grey Lists](https://www.fatf-gafi.org/en/countries/black-and-grey-lists.html); [FFIEC](https://bsaaml.ffiec.gov/manual/RisksAssociatedWithMoneyLaunderingAndTerroristFinancing/07) | Wire to/from FATF-listed or OFAC-sanctioned country | `def detect_high_risk_wire(txn, high_risk_countries)` — Country lookup | `feat_high_risk_country_wire_ratio(txns)` — High-risk wires / total wires |
| 17 | **Wire Layering (Fan-Out)** | [Flagright](https://www.flagright.com/post/developing-effective-transaction-monitoring-rules) | Single incoming wire split into multiple outgoing wires | `def detect_fan_out(txns, min_recipients=3, hours=48)` — Count unique outgoing recipients after incoming | `feat_fan_out_ratio(txns)` — out_degree / in_degree |
| 18 | **Wire Layering (Fan-In)** | [Flagright](https://www.flagright.com/post/developing-effective-transaction-monitoring-rules) | Multiple incoming wires consolidated into single outgoing | `def detect_fan_in(txns, min_senders=3, hours=72)` — Count unique incoming senders before outgoing | `feat_fan_in_ratio(txns)` — in_degree / out_degree |
| 19 | **DR-US Corridor Remittance Abuse** | [FinCEN GTO](https://www.fincen.gov/news/news-releases/treasury-cracks-down-remittances-dominican-republic); [Inter-American Dialogue](https://thedialogue.org/blogs/2025/08/the-marketplace-for-money-transfers-to-the-dominican-republic-an-assessment) | High-frequency/value remittances on US-DR corridor inconsistent with income | `def detect_corridor_abuse(txns, corridor='US-DR', income_multiple=3)` — Flag when corridor volume > 3x income | `feat_remittance_to_income_ratio(txns, acct)` — Corridor volume / declared income |
| 20 | **Remittance Structuring** | [FinCEN GTO](https://home.treasury.gov/news/press-releases/rr1904) | Multiple remittances below $10K from NY to DR (FinCEN imposed $750 reporting threshold) | `def detect_remittance_structuring(txns, threshold=10000, low=750)` — Aggregate remittances in window | `feat_remittance_sender_diversity(txns)` — Unique senders count |
| 21 | **Unusual Remittance Patterns** | [INCSR](https://www.state.gov/2025-international-narcotics-control-strategy-report) | Remittances inconsistent with stated income/occupation; round-dollar amounts | `def detect_unusual_remittance(txns, acct, income_multiple=3)` — Compare volume to stated income | `feat_remittance_avg_amount(txns)` — Mean remittance value |
| 22 | **Bulk Cash Smuggling Indicators** | [INCSR Vol 2](https://www.state.gov/wp-content/uploads/2025/01/2024-INCSR-Vol-2-Money-Laundering-Accessible-Version.pdf); [DEA](https://www.dea.gov/press-releases) | Large cash deposits inconsistent with business type, followed by remittance | `def detect_bulk_cash_courier(txns, acct)` — Cash deposit > 2x industry avg + followed by wire | `feat_cash_deposit_deviation_from_industry(txns, acct)` — Cash vs industry mean |
| 23 | **P2P Rapid Disbursement** | [AMLTRIX](https://framework.amltrix.com/techniques/T0134.001); [Abrigo](https://www.abrigo.com/blog/p2p-fraud-and-emerging-aml-trends/) | 10+ P2P payments to unique recipients in < 24h | `def detect_p2p_rapid(txns, min_recipients=10, hours=24)` — Count unique P2P recipients | `feat_p2p_unique_recipients_24h(txns)` — Distinct recipients in 24h |
| 24 | **P2P Collection Pattern** | [Sanction Scanner](https://www.sanctionscanner.com/blog/aml-and-compliance-solution-for-the-peer-2-peer-industry-489) | P2P receipts from 10+ unique senders aggregating > $5K | `def detect_p2p_collection(txns, min_senders=10, threshold=5000)` — Aggregate incoming P2P | `feat_p2p_sender_diversity(txns)` — Unique P2P senders |
| 25 | **Cross-Channel Layering** | [Financial Integrity Institute](https://finintegrity.org/from-cash-to-clicks-aml-challenges-typologies-for-digital-payments/) | Funds moved across 3+ channels (cash→P2P→wire) within 48h | `def detect_cross_channel(txns, min_channels=3, hours=48)` — Count distinct channels used | `feat_channel_entropy_48h(txns)` — Shannon entropy of channels in 48h |
| 26 | **ACH Unauthorized Debit** | [Nacha Phase 1](https://www.nacha.org/rules/risk-management-topics-fraud-monitoring-phase-1); [FFIEC ACH](https://bsaaml.ffiec.gov/manual/RisksAssociatedWithMoneyLaunderingAndTerroristFinancing/08) | ACH debit with no authorization history | `def detect_unauthorized_ach(txn, acct)` — Check originator against authorized list | `feat_new_ach_originator_flag(txn, acct)` — Boolean: originator not in history |
| 27 | **Ghost Employee Payroll** | [Nacha Phase 2](https://www.nacha.org/rules/risk-management-topics-fraud-monitoring-phase-2) | Multiple payroll credits from different employers to single account | `def detect_ghost_payroll(txns)` — Count distinct payroll originators | `feat_distinct_payroll_sources(txns)` — Count unique employers |
| 28 | **FX Structuring** | [ComplyAdvantage](https://complyadvantage.com/insights/aml-risk-foreign-exchange/) | Multiple FX conversions each below threshold | `def detect_fx_structuring(txns, threshold=10000, window_days=5)` — Aggregate FX amounts | `feat_fx_aggregate_vs_threshold(txns)` — FX sum / threshold |
| 29 | **Peso Exchange Scheme** | [FinCrime Central DR 2025](https://fincrimecentral.com/aml-foreign-exchange-dominican-republic-2025/); [FinCEN](https://www.fincen.gov/resources/advisories/fincen-advisory-fin-2010-a001) | High-volume DOP/USD exchanges inconsistent with profile | `def detect_peso_exchange(txns, acct)` — FX volume > 3x expected | `feat_fx_volume_vs_expected(txns, acct)` — Actual / expected FX volume |
| 30 | **Real Estate ML (DR-Specific)** | [INCSR](https://2009-2017.state.gov/j/inl/rls/nrcrpt/2016/vol2/253396.htm); [FATF MER 2018](https://www.fatf-gafi.org/en/publications/Mutualevaluations/Mer-dominican-republic-2018.html) | Large payments to real estate/construction entities, especially cash-funded | `def detect_real_estate_ml(txns)` — Flag cash-funded payments to RE entities > $50K | `feat_real_estate_payment_to_income_ratio(txns, acct)` — RE payments / income |
| 31 | **FTZ/Trade-Based ML** | [OECD](https://www.oecd.org/content/dam/oecd/en/publications/reports/2022/12/free-trade-zones-and-illicit-gold-flows-in-latin-america-and-the-caribbean_220669c5/7536db96-en.pdf); [FinCEN](https://www.fincen.gov/resources/advisories/fincen-advisory-fin-2010-a001) | Over/under invoicing through FTZs; gold laundering through pawnbroker networks | `def detect_ftz_tbml(txns, ftz_entities)` — Flag irregular patterns with FTZ counterparties | `feat_ftz_txn_amount_variance(txns)` — Variance of FTZ-related txn amounts |
| 32 | **Gold/Precious Metals Transactions** | [OECD FTZ Gold Report](https://www.oecd.org/content/dam/oecd/en/publications/reports/2022/12/free-trade-zones-and-illicit-gold-flows-in-latin-america-and-the-caribbean_220669c5/7536db96-en.pdf) | Gold/jewelry purchases through dealers, pawnbrokers, FTZ entities | `def detect_gold_txns(txns, gold_mcc_codes, threshold=5000)` — Flag gold merchant txns | `feat_gold_txn_frequency(txns)` — Gold-related txn count |
| 33 | **Casino/Gaming Transactions** | [iGamingToday](https://www.igamingtoday.com/dominican-republic-signs-agreement-with-fiba-to-strengthen-anti-money-laundering-controls-in-gambling-sector/); [FATF MER 2018](https://www.fatf-gafi.org/en/publications/Mutualevaluations/Mer-dominican-republic-2018.html) | Frequent/large casino transactions disproportionate to customer profile | `def detect_casino_ml(txns, acct)` — Casino volume > 50% of monthly income | `feat_casino_txn_ratio(txns)` — Casino volume / total volume |
| 34 | **OFAC/Sanctions Screening** | [OFAC SDN List](https://ofac.treasury.gov/recent-actions/20190820); [Treasury Peralta DTO](https://home.treasury.gov/news/press-releases/sm755) | Transactions involving OFAC-designated persons/entities (Peralta, Calderon Rijo, Bautista) | `def screen_ofac(counterparty, sdn_list, fuzzy_threshold=0.85)` — Fuzzy name match | `feat_sanctions_near_miss_count(acct)` — Count of near-miss name matches |
| 35 | **PEP Transaction Monitoring** | [Law 155-17](https://drlawyer.com/new-dominican-money-laundering-law-no-155-17/); [FATF R.12](https://www.fatf-gafi.org/en/countries/black-and-grey-lists.html) | Enhanced monitoring for PEPs and associates; unusual patterns | `def detect_pep_activity(txn, acct)` — PEP flag + txn > 50% expected monthly | `feat_pep_activity_vs_declared_income(txns, acct)` — Volume / declared income |
| 36 | **Fentanyl/Drug Trafficking Financial Indicators** | [DEA 2024-2025 Press Releases](https://www.dea.gov/press-releases); [FinCEN Fentanyl FTA](https://www.fincen.gov/system/files/shared/FinCEN-FTA-Fentanyl.pdf) | Sudden unexplained wealth; cash fronts; wires to Mexico/Colombia; online pharmacy payments | `def detect_sudden_wealth(acct, pct=500, days=30)` — 5x balance increase in 30 days | `feat_balance_growth_rate(acct)` — Balance slope over 30d |
| 37 | **Human Trafficking Financial Indicators** | [TIP Report 2025](https://www.state.gov/reports/2025-trafficking-in-persons-report/dominican-republic/); [FinCEN](https://www.fincen.gov/resources/advisories/fincen-advisory-fin-2010-a001) | Multiple persons depositing into single account; hotel/transport payments; structured payroll | `def detect_trafficking_indicators(txns, acct)` — 5+ unique senders + hotel/transport MCC | `feat_unique_depositor_count(txns)` + `feat_hotel_transport_txn_ratio(txns)` |
| 38 | **Cocaine Transit Financial Indicators** | [DEA](https://www.dea.gov/press-releases); [INCSR](https://www.state.gov/2025-international-narcotics-control-strategy-report) | Payments to shipping/logistics/maritime entities; port-related transactions | `def detect_maritime_logistics(txns, shipping_mccs, port_entities)` — Flag large shipping payments | `feat_shipping_txn_frequency(txns)` — Shipping/logistics txn count |
| 39 | **Shell Company Indicators** | [FATF MER 2018 IO.5](https://www.fatf-gafi.org/en/publications/Mutualevaluations/Mer-dominican-republic-2018.html); [Financial Crime Academy](https://financialcrimeacademy.org/red-flags-in-high-risk-industries/) | Entity with no employees, nominee directors, secrecy jurisdiction, no operating expenses | `def detect_shell_company(entity)` — Composite check: no employees + nominee + no expenses | `feat_company_age_vs_activity(entity)` + `feat_expense_to_revenue_ratio(txns)` |
| 40 | **Dormant Account Reactivation** | [IBM](https://www.ibm.com/think/topics/aml-transaction-monitoring) | Account inactive 90+ days suddenly receiving large deposits or high activity | `def detect_dormant_reactivation(acct, txns, dormant_days=90, amount=5000)` — Inactivity then deposit | `feat_days_since_last_activity(acct)` + `feat_reactivation_amount_vs_historical(acct)` |
| 41 | **Circular Fund Flow (Network)** | [Linkurious](https://linkurious.com/blog/anti-money-laundering-use-cases-graph-analytics/); [Oracle](https://www.oracle.com/financial-services/aml-financial-crime-compliance/graph-analytics-powers-the-game/) | Funds leaving account and returning via different path (A→B→C→A) | `def detect_circular_flow(graph, acct, max_hops=5)` — Cycle detection in directed graph | `feat_circular_flow_count(graph, acct)` — Count of cycles involving account |
| 42 | **Shared Identity Attributes** | [McKinsey](https://www.mckinsey.com/industries/financial-services/our-insights/banking-matters/network-analytics-and-the-fight-against-money-laundering); [Linkurious](https://linkurious.com/blog/anti-money-laundering-use-cases-graph-analytics/) | 3+ accounts sharing phone, address, email, or IP | `def detect_shared_identity(acct, all_accounts)` — Find accounts with shared PII | `feat_shared_attribute_count(acct)` — Count of accounts sharing any PII |
| 43 | **Informal Value Transfer (Hawala)** | [FATF MER 2018](https://www.fatf-gafi.org/en/publications/Mutualevaluations/Mer-dominican-republic-2018.html) | Circular/reciprocal transactions between unrelated parties; third-party transfers | `def detect_circular_txns(txns, graph, cycle_length=3)` — Detect A→B→C→A patterns | `feat_counterparty_reciprocity_ratio(txns)` — Reciprocal txn ratio |
| 44 | **Currency Exchange Anomalies** | [FinCrime Central 2025](https://fincrimecentral.com/aml-foreign-exchange-dominican-republic-2025/); [ComplyAdvantage](https://complyadvantage.com/insights/aml-risk-foreign-exchange/) | Frequent FX below threshold; off-market rate acceptance; round-trip FX | `def detect_fx_anomaly(txns)` — Aggregate: FX structuring + rate tolerance + round-trip | `feat_fx_frequency(txns)` + `feat_fx_purpose_consistency(txns)` |
| 45 | **Corruption/Bribery Indicators** | [TI CPI DR](https://www.transparency.org/en/countries/dominican-republic); [OFAC Bautista](https://home.treasury.gov/news/press-releases/sm0411) | Government contract payments to PEP-linked entities; unusual payments to officials | `def detect_corruption(txns, pep_list, gov_entities)` — Link gov contract payments to PEP connections | `feat_pep_connection_score(acct)` + `feat_gov_contract_payment_regularity(txns)` |
| 46 | **Cash-Intensive Business Front** | [INCSR](https://2009-2017.state.gov/j/inl/rls/nrcrpt/2016/vol2/253396.htm); [FFIEC CIB](https://bsaaml.ffiec.gov/manual/RisksAssociatedWithMoneyLaunderingAndTerroristFinancing/29) | Colmados, car washes, salons with revenue inconsistent with type/size/location | `def detect_cash_business_outlier(acct, industry_benchmark)` — Revenue > 2 std from benchmark | `feat_revenue_per_sqft(acct)` + `feat_revenue_consistency_vs_peers(acct)` |
| 47 | **Commingling Personal/Business** | [FFIEC Appendix F](https://bsaaml.ffiec.gov/manual/Appendices/07); [AML Watcher](https://amlwatcher.com/blog/how-commingling-blur-the-lines-between-legitimate-illegal-wealth/) | Frequent transfers between owner's personal and business accounts | `def detect_commingling(personal_txns, business_txns, owner_id)` — Cross-transfers >= 5 | `feat_personal_business_transfer_count(txns, owner_accounts)` |
| 48 | **Vendor Kickback Pattern** | [FFIEC Appendix F](https://bsaaml.ffiec.gov/manual/Appendices/07) | Business pays vendor, then receives cash deposit of similar amount | `def detect_vendor_kickback(txns, days=7)` — Pair vendor payments with subsequent cash deposits | `feat_vendor_payment_cash_return_correlation(txns)` |
| 49 | **New Account High Activity** | [Nacha Phase 1](https://www.nacha.org/rules/risk-management-topics-fraud-monitoring-phase-1) | Account < 30 days old with high transaction volume/value | `def detect_new_account_burst(acct, txns)` — Age < 30 days + volume > $50K or count > 20 | `feat_activity_per_account_age_day(acct, txns)` — Volume / age in days |
| 50 | **Off-Hours Transaction Concentration** | [Sanctions.io](https://www.sanctions.io/blog/anti-money-laundering-aml-transaction-monitoring-rules-and-best-practices) | > 30% of transactions between midnight-5 AM | `def detect_off_hours(txns, pct_threshold=0.3)` — Off-hours txn ratio | `feat_off_hours_ratio(txns)` — Off-hours count / total |
| 51 | **Peer Group Deviation** | [Solytics](https://www.solytics-partners.com/resources/case-studies/peer-group-analysis-for-aml-transaction-monitoring); [FICO](https://www.fico.com/blogs/using-ai-and-machine-learning-improve-aml) | Customer activity significantly deviates from peer norms (> 3 std) | `def detect_peer_deviation(acct, peer_group, metric, threshold_std=3)` — Z-score comparison | `feat_peer_zscore(acct, peer_group, metric)` — (value - peer_mean) / peer_std |
| 52 | **Correspondent Banking Pass-Through** | [CSIS](https://www.csis.org/analysis/there-new-normal-de-risking-caribbean); [FSB](https://caribbeanderisking.com/) | Nested accounts providing indirect access to US financial system | `def detect_nested_passthrough(txns)` — Wire in/out ratio > 0.9 with 10+ txns | `feat_wire_in_out_symmetry(txns)` + `feat_unique_originator_count(txns)` |
| 53 | **Tax Evasion Integration** | [Law 155-17](https://drlawyer.com/new-dominican-money-laundering-law-no-155-17/) (predicate offense) | Deposits inconsistent with tax filings; revenue far exceeding declarations | `def detect_tax_mismatch(acct, declared_income, deposits, tolerance=1.5)` — Deposits > 1.5x declared | `feat_deposit_to_declared_income_ratio(txns, acct)` |
| 54 | **Velocity Spike (Any Channel)** | [Sumsub](https://sumsub.com/blog/transaction-monitoring/) | Transaction count/volume dramatically exceeds historical baseline (> 300%) | `def detect_velocity_spike(txns, multiplier=3, window=7, baseline=90)` — Current vs baseline | `feat_velocity_ratio_7d_vs_90d(txns)` — 7d count / (90d / 13) |
| 55 | **Black Market Peso Exchange** | [Financial Crime Academy BMPE](https://financialcrimeacademy.org/black-market-peso-exchange-money-laundering/); [INCSR](https://2009-2017.state.gov/j/inl/rls/nrcrpt/2016/vol2/253396.htm) | Drug proceeds converted to pesos through trade-based scheme involving DR businesses | `def detect_bmpe_indicators(txns)` — Unusual trade payments + FX + cash patterns | `feat_trade_fx_cash_correlation(txns)` — Correlation of trade, FX, and cash flows |
| 56 | **Nightclub/Entertainment Laundering** | [Treasury Peralta DTO](https://home.treasury.gov/news/press-releases/sm755); [InSight Crime](https://insightcrime.org/news/brief/dominican-republic-massive-money-laundering/) | Cash-intensive entertainment businesses as ML fronts (Peralta case: $260M+ through nightclubs) | `def detect_nightclub_ml(txns, acct)` — Cash deposits > 300% peer avg for entertainment | `feat_entertainment_biz_cash_peer_percentile(txns, peer_group)` |
| 57 | **Fuel Station Laundering** | [Dominican Today - Op Falcon](https://dominicantoday.com/dr/local/2021/09/10/27-nabbed-in-biggest-dominican-drug-bust/) | Fuel stations used as ML assets (7 seized in Operation Falcon) | `def detect_fuel_station_anomaly(txns, acct)` — Revenue vs fuel volume discrepancy | `feat_fuel_revenue_vs_volume_ratio(txns, acct)` |
| 58 | **Tourism Agency ML** | [INCSR](https://2009-2017.state.gov/j/inl/rls/nrcrpt/2016/vol2/253396.htm) | Tourism agencies identified as ML facilitators in DR | `def detect_tourism_agency_ml(txns, acct)` — Cash-heavy tourism entity with unusual wire patterns | `feat_tourism_agency_cash_ratio(txns)` |
| 59 | **Car Dealership ML** | [INCSR](https://2009-2017.state.gov/j/inl/rls/nrcrpt/2016/vol2/253396.htm) | Car dealerships contributing to money laundering | `def detect_car_dealer_ml(txns, acct)` — High-value cash purchases without financing | `feat_car_dealer_cash_purchase_ratio(txns)` |
| 60 | **Real Estate Tokenization Risk** | [El Inmobiliario](https://inmobiliario.do/en/real-estate-tokenization-in-the-dominican-republic-financial-innovation-or-risk-to-the-dominican-real-estate-registry-system-/) | Tokenized real estate obscuring beneficial ownership | `def detect_tokenized_re(txns)` — Flag txns to tokenization platforms + real estate | `feat_tokenized_asset_txn_count(txns)` — Count of tokenization-related txns |
| 61 | **Foreign National with DR Account + Origin-Country Travel** | [INCSR](https://www.state.gov/2025-international-narcotics-control-strategy-report); [FATF MER 2018](https://www.fatf-gafi.org/en/publications/Mutualevaluations/Mer-dominican-republic-2018.html) | Mexican/Colombian/Venezuelan national holds DR account but shows frequent card usage in origin country or known transit hubs — suggests DR account used as layering vehicle rather than primary banking | `def detect_foreign_national_origin_travel(acct, txns, high_risk_nationalities=['MX','CO','VE'])` — Flag when nationality ∈ high-risk AND >30% of card txns geolocated to origin country | `feat_nationality_txn_geography_mismatch(acct, txns)` — % of txns in countries other than residency or nationality |
| 62 | **DR Resident with Anomalous Mexico Travel** | [DEA 2024-2025 Press Releases](https://www.dea.gov/press-releases); [FinCEN Fentanyl FTA](https://www.fincen.gov/system/files/shared/FinCEN-FTA-Fentanyl.pdf) | DR citizen/resident with recurring POS/ATM usage in Mexico (especially Sinaloa, Jalisco, Guerrero) with no declared business reason — Sinaloa cartel nexus indicator | `def detect_dr_mexico_travel(acct, txns, mexico_states=['SIN','JAL','GRO'])` — Flag DR resident with >=3 Mexico txns in 90d and no declared MX business | `feat_mexico_txn_ratio_30d(txns)` — Mexico POS/ATM transactions / total |
| 63 | **US–DR Corridor Mule Profile** | [FinCEN GTO](https://www.fincen.gov/news/news-releases/treasury-cracks-down-remittances-dominican-republic); [DEA Press Releases](https://www.dea.gov/press-releases) | DR account receiving frequent small remittances from US Northeast (NJ/NY/MA/CT) followed by rapid ATM cashout — consistent with drug proceeds repatriation via money mule network | `def detect_us_dr_mule(txns, acct, ne_states=['NJ','NY','MA','CT'], cashout_hours=48)` — Flag when >=5 remittances from NE states in 30d AND >80% withdrawn via ATM within 48h | `feat_us_northeast_remittance_ratio(txns)` — Remittances from NJ/NY/MA/CT / total incoming |
| 64 | **Nightclub/Entertainment Lifestyle + Cash Pattern** | [Treasury Peralta DTO](https://home.treasury.gov/news/press-releases/sm755); [InSight Crime](https://insightcrime.org/news/brief/dominican-republic-massive-money-laundering/) | High nightclub/bar MCC spend, luxury goods purchases, late-night transaction concentration, followed by next-day cash deposits — lifestyle pattern associated with DTO operatives and front businesses | `def detect_nightlife_cash_pattern(txns, nightclub_mccs=[5813,7911,5812], luxury_mccs=[5944,5945])` — Flag when nightclub MCC >20% of spend AND late-night ratio >30% AND next-day cash deposits | `feat_nightclub_mcc_spend_ratio_30d(txns)` — MCC 5813/7911/5812 spend / total |
| 65 | **Cross-Border ATM Corridor Pattern** | [FFIEC Appendix F](https://bsaaml.ffiec.gov/manual/Appendices/07); [Feedzai](https://www.feedzai.com/blog/what-is-aml-transaction-monitoring/) | ATM usage in both US and DR within short time windows (24-72h), suggesting physical courier travel carrying cash or cards — extends ATM-006 impossible travel to corridor-level pattern | `def detect_cross_border_atm_corridor(txns, countries=['US','DO'], window_hours=72)` — Flag when ATM txns in both US and DR within 72h window, recurring >=3 times in 90d | `feat_cross_border_atm_pair_count_90d(txns)` — Count of US-DR ATM usage pairs within 72h windows |
| 66 | **Fentanyl Distribution Financial Profile** | [FinCEN Fentanyl FTA](https://www.fincen.gov/system/files/shared/FinCEN-FTA-Fentanyl.pdf); [DEA 2024-2025 Press Releases](https://www.dea.gov/press-releases) | Regular incoming transfers from US Northeast, small-to-mid wire/remittance amounts ($500-$5K), spending inconsistent with declared income — financial footprint matching prosecuted Dominican fentanyl distributors | `def detect_fentanyl_financial_profile(txns, acct, ne_states=['NJ','NY','MA','CT'])` — Flag when NE remittances >50% of income AND avg amount $500-$5K AND spending >2x declared income | `feat_us_northeast_remittance_ratio(txns)` + `feat_deposit_to_declared_income_ratio(txns, acct)` |
| 67 | **PEP Lifestyle Inconsistency (Geo-Based)** | [Law 155-17](https://drlawyer.com/new-dominican-money-laundering-law-no-155-17/); [TI CPI DR](https://www.transparency.org/en/countries/dominican-republic) | Government official salary but luxury spending in tourist zones (Punta Cana, Casa de Campo, Cap Cana), high foreign travel frequency — geographic spending pattern inconsistent with declared PEP income | `def detect_pep_geo_inconsistency(acct, txns, tourist_zones=['PUNTA_CANA','CASA_CAMPO','CAP_CANA'])` — Flag PEP with tourist zone spend >20% of income OR foreign travel txns >10/quarter | `feat_geo_lifestyle_inconsistency_score(acct, txns)` — Composite: declared income vs. geo-spending pattern mismatch |
| 68 | **Tourist Zone Transaction Anomaly** | [FATF MER 2018](https://www.fatf-gafi.org/en/publications/Mutualevaluations/Mer-dominican-republic-2018.html); [INCSR](https://www.state.gov/2025-international-narcotics-control-strategy-report) | Non-tourist-sector client with high transaction volumes in Punta Cana, Bávaro, Samaná, La Romana — suggests use of tourist zones for layering or cash placement through hospitality businesses | `def detect_tourist_zone_anomaly(acct, txns, zones=['PUNTA_CANA','BAVARO','SAMANA','LA_ROMANA'])` — Flag non-tourism client with >15% of txns in tourist zones | `feat_tourist_zone_txn_ratio(txns)` — Tourist zone txn count / total for non-tourism clients |
| 69 | **Multi-Country Card Usage (Transit Profile)** | [DEA](https://www.dea.gov/press-releases); [INCSR](https://www.state.gov/2025-international-narcotics-control-strategy-report) | Card used in 3+ countries within 30 days matching known drug transit routes (DR→PR→US, DR→Haiti→Colombia, DR→Venezuela→Colombia) — physical movement along trafficking corridors | `def detect_transit_route_card(txns, transit_routes=[['DO','PR','US'],['DO','HT','CO'],['DO','VE','CO']])` — Flag when card used in >=3 countries in 30d AND route matches known transit corridor | `feat_transit_route_country_count_30d(txns)` — Distinct countries on known drug transit routes in 30 days |
| 70 | **Nationality–Residency–Transaction Geography Mismatch** | [FATF R.10-12](https://www.fatf-gafi.org/en/topics/fatf-recommendations.html); [INCSR](https://www.state.gov/2025-international-narcotics-control-strategy-report) | Declared DR resident but 40%+ transactions in foreign country; or foreign national but no transactions in declared home country — mismatch between declared profile and actual transaction geography suggests account misuse | `def detect_residency_txn_mismatch(acct, txns, mismatch_threshold=0.4)` — Flag when foreign txn ratio >40% for residents OR home country txn ratio <5% for foreign nationals | `feat_nationality_txn_geography_mismatch(acct, txns)` — % of txns in countries other than residency or nationality |

---

## 9. Risk Assessment Matrix

| Risk Dimension | Level | Key Evidence |
|---|---|---|
| **Drug Transit** | **Critical** | 120+ tons cocaine/year; US Major Drug Transit designation; 30+ tons seized 2024 |
| **Informal Economy** | **Very High** | 54.7% informal employment; cash-dominant; large unbanked population |
| **Money Laundering** | **High** | INCSR "major ML country"; TBML, bulk cash, real estate, casinos, nightclubs |
| **Remittance/Financial Flow** | **High** | $10.8B annual corridor; 80%+ from US; FinCEN GTOs issued |
| **Corruption** | **High** | CPI 37/100; DEA office closed for corruption; judiciary weakness |
| **Fentanyl Distribution** | **High** | Growing trend; 6+ DEA prosecutions 2024-2025; US Northeast distribution |
| **Human Trafficking** | **Moderate-High** | Tier 2 TIP; 100K+ stateless; forced labor + sex trafficking documented |
| **FATF/Regulatory** | **Medium** | Not on grey/black list but weak effectiveness; supervisory oversight "Low" |
| **Sanctions** | **Moderate** | Active OFAC designations (Peralta, Calderon Rijo, Bautista) |
| **Correspondent Banking** | **Moderate** | Regional de-risking; DR insulated by economic size |
| **Legal Framework** | **Moderate** | Law 155-17 comprehensive but enforcement/supervision remain weak |

---

## 10. Reference Documents

All supporting research is stored in the `reference/` folder:

| Document | Contents |
|---|---|
| [reference/DR_AML_Country_Risk_Profile.md](reference/DR_AML_Country_Risk_Profile.md) | Jurisdiction risk: FATF, INCSR, Basel AML Index, CPI, legal framework, vulnerabilities, OFAC, correspondent banking, 25-row typology table |
| [reference/DR_Narcotics_Trafficking_AML_Research.md](reference/DR_Narcotics_Trafficking_AML_Research.md) | Narcotics trafficking routes, fentanyl, cartel nexus, human trafficking, TBML, ML typologies, enforcement actions, drug seizure statistics |
| [reference/AML_Transaction_Monitoring_Research.md](reference/AML_Transaction_Monitoring_Research.md) | 71 rule-based monitoring rules by channel, 88 anomaly detection features, 25 small business rules, FATF/Wolfsberg standards, 40-row comprehensive table |

### Summary of Coverage
- **70 red flags/typologies** in consolidated table (Section 8)
- **71 rule-based monitoring rules** across 7 channels
- **25 small business-specific rules**
- **96 anomaly detection features** across 6 categories
- **140+ source references** with URLs

---

*Document compiled: 2026-02-23*
*All sources publicly available and URLs verified at time of research*
