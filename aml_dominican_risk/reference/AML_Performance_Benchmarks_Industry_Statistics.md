# AML Performance Benchmarks & Industry Statistics
## Calibrating Expected Model Performance for a Retail Bank in the Dominican Republic
### Date: 2026-02-24

---

## Table of Contents
1. [STR Filing Rates](#1-str-filing-rates)
2. [False Positive Rates](#2-false-positive-rates)
3. [Recall / Detection Rates](#3-recall--detection-rates)
4. [Precision Benchmarks](#4-precision-benchmarks)
5. [Base Rates — Prevalence of Illicit Actors](#5-base-rates--prevalence-of-illicit-actors)
6. [FATF Effectiveness Ratings — Dominican Republic](#6-fatf-effectiveness-ratings--dominican-republic)
7. [Comparable Jurisdiction Data](#7-comparable-jurisdiction-data)
8. [AI/ML System Improvement Benchmarks](#8-aiml-system-improvement-benchmarks)
9. [Summary: Recommended Targets for DR Retail Bank](#9-summary-recommended-targets-for-dr-retail-bank)

---

## 1. STR Filing Rates

### 1.1 United States (FinCEN SAR Data)

| Metric | Value | Year | Source |
|--------|-------|------|--------|
| Total SARs filed (all industries) | 4.7 million | FY 2024 | [FinCEN Year in Review FY2024](https://www.fincen.gov/system/files/2025-08/FinCEN-Infographic-Public-2025-508.pdf) |
| SARs by depository institutions (banks) | 2.6 million | FY 2024 | [ABA Banking Journal](https://bankingjournal.aba.com/2025/06/fincen-releases-figures-on-bsa-filings/) |
| Total SARs filed (all industries) | 4.6 million | FY 2023 | [FinCEN FY2023](https://www.moneylaunderingnews.com/2024/06/fincen-releases-year-in-review-for-fy-2023-sars-ctrs-and-information-sharing/) |
| Average daily SAR filings | 12,870/day | FY 2024 | [FinCEN](https://www.fincen.gov/reports/sar-stats) |
| SAR growth 2020-2024 | +51.8% | 2020-2024 | [NICE Actimize](https://www.niceactimize.com/blog/fraud-prevention-insights-from-unpacking-the-2024-fincen-sar-stats) |
| Number of FDIC-insured banks | ~4,462 | 2024 | [FDIC](https://www.fdic.gov/quarterly-banking-profile/fdic-statistics-glance) |
| % US households banked | 96% | 2023 | [FDIC Survey](https://www.fdic.gov/news/press-releases/2024/fdic-survey-finds-96-percent-us-households-were-banked-2023) |

**Derived filing rate (US depository institutions):**
- ~130 million US households × 96% banked ≈ 125 million banked households
- Multiple accounts per household → estimated 300-350 million bank accounts
- 2.6 million SARs / ~325 million accounts ≈ **~8 SARs per 1,000 accounts/year**
- Note: This is a rough estimate; FinCEN does not publish a normalized per-account rate

### 1.2 Canada (FINTRAC Data)

| Metric | Value | Year | Source |
|--------|-------|------|--------|
| Total STRs filed | 631,137 | FY 2023-24 | [IJF/FINTRAC investigation](https://theijf.org/fintrac-police-disclosures) |
| Total STRs filed | ~586,000 | FY 2021-22 | [FINTRAC reporting](https://fintrac-canafe.canada.ca/guidance-directives/transaction-operation/str-dod/str-dod-eng) |
| Notable penalties (TD Bank) | C$9.18 million | 2024 | FINTRAC enforcement |
| Notable penalties (RBC) | C$7.5 million | 2023 | FINTRAC enforcement |

**Derived filing rate (Canada):**
- Canada has ~38 million population, ~37 million banked adults
- Multiple accounts → ~80-100 million accounts
- 631K STRs / ~90M accounts ≈ **~7 STRs per 1,000 accounts/year**

### 1.3 Latin America / High-Risk Jurisdictions

| Jurisdiction | Context | Source |
|-------------|---------|--------|
| Dominican Republic | UAF receives Suspicious Operation Reports (ROS); entities must report within 5 business days. Specific filing volumes not publicly available | [UAF](https://www.uaf.gob.do/) |
| Dominican Republic | Reporting threshold: cash transactions exceeding $10,000 (USD equivalent) | [Sanction Scanner](https://www.sanctionscanner.com/aml-guide/anti-money-laundering-aml-in-dominican-republic-604) |
| Haiti | Highest ML/TF risk in LatAm (index score 7.92 in 2024) | [Statista](https://www.statista.com/statistics/817990/risk-index-money-laundering-terrorist-financing-latin-america/) |
| Venezuela | Second highest ML/TF risk (index score 7.59) | [Statista](https://www.statista.com/statistics/817990/risk-index-money-laundering-terrorist-financing-latin-america/) |

**Note**: Most LatAm FIUs do not publicly report STR filing volumes with the same granularity as FinCEN or FINTRAC. The Dominican Republic's UAF uses the goAML system for reporting but does not publish aggregate statistics externally.

### 1.4 Dominican Republic Banking Sector Context

| Metric | Value | Source |
|--------|-------|--------|
| Number of banking entities | 49 (18 multiple banks, 15 savings/credit banks, 10 S&L, 4 credit corps, 2 public) | [Trade.gov](https://www.trade.gov/country-commercial-guides/dominican-republic-financial-services) |
| Total bank assets | RD$4,146,464 million (~US$70B) | As of Nov 2025 |
| Bank accounts per 1,000 adults | 772 | 2020, [FRED/World Bank](https://fred.stlouisfed.org/series/DDAI01DOA642NWDB) |
| DR population | ~11.2 million | 2024 |
| Estimated total bank accounts | ~5-6 million (772 per 1,000 adults × ~7.5M adults) | Derived from World Bank data |

---

## 2. False Positive Rates

### 2.1 Rule-Based Systems (Industry Benchmarks)

| Metric | Value | Source |
|--------|-------|--------|
| Alert false positive rate (traditional/rule-based) | **90-95%** | [PwC estimate](https://www.flagright.com/post/understanding-false-positives-in-transaction-monitoring) |
| Alert false positive rate (broader range) | **92-97%** | [AML Watcher](https://amlwatcher.com/blog/how-to-manage-healthy-aml-false-positive-in-2024/) |
| Extreme unproductive scenarios | **Up to 99.5%** | [DataVisor](https://www.datavisor.com/blog/guest-post-end-the-false-positive-alerts-plague-in-anti-money-laundering-aml-systems/) |
| Industry cost of false positives | ~$3.5B/year in wasted investigation | [Various industry estimates](https://www.flagright.com/post/understanding-false-positives-in-transaction-monitoring) |

### 2.2 Alert-to-SAR Conversion Rates (Inverse of FP at Alert Level)

| System Type | Alert-to-SAR Rate | FP Rate | Source |
|-------------|-------------------|---------|--------|
| Rule-based systems (typical) | **1-5%** | 95-99% | [DataRobot](https://docs.datarobot.com/en/docs/get-started/gs-dr5/biz-accelerators/money-launder.html) |
| Rule-based (MBCA mid-size bank study) | **2.8%** (108 SARs / 3,908 alerts) | 97.2% | [Jim Richards, LinkedIn](https://www.linkedin.com/pulse/rules-based-monitoring-alert-sar-ratios-false-rates-we-jim-richards) |
| Alert-to-case rate (MBCA mid-size bank) | **8.9%** (348 cases / 3,908 alerts) | — | Same source |
| Case-to-SAR rate (MBCA mid-size bank) | **31%** (108 SARs / 348 cases) | — | Same source |
| Human referral systems (bank employees) | **40-50%** | 50-60% | [Jim Richards](https://www.linkedin.com/pulse/rules-based-monitoring-alert-sar-ratios-false-rates-we-jim-richards) |
| AI/ML enhanced systems | **5-15%** (target) | 85-95% | Various vendor claims |
| Agentic AI approaches | **~80-85%** useful alerts | ~15-20% FP | [Flagright](https://www.flagright.com/post/ai-and-the-future-of-aml-compliance) |

### 2.3 Key Case Study: MBCA Mid-Size Bank (2018)

This is one of the most detailed publicly available benchmarks:

| Stage | Count | Rate |
|-------|-------|------|
| Monthly alerts generated | 3,908 | 100% |
| Cases opened (escalated from alerts) | 348 | 8.9% of alerts |
| SARs filed | 108 | 2.8% of alerts, 31% of cases |
| Alerts closed (no action) | ~3,560 | 91.1% |

**Source**: Mid-Size Bank Coalition of America, cited in [Jim Richards analysis](https://www.linkedin.com/pulse/rules-based-monitoring-alert-sar-ratios-false-rates-we-jim-richards)

---

## 3. Recall / Detection Rates

### 3.1 The "Dark Number" — What Fraction of ML Is Detected?

| Estimate | Value | Source |
|----------|-------|--------|
| **Criminal proceeds seized globally** | **~1%** of laundered funds | [UNODC](https://www.unodc.org/unodc/en/money-laundering/overview.html) |
| Criminal proceeds recovered | **0.1%** of criminal funds | [LegalJobs](https://legaljobs.io/blog/money-laundering-statistics/) |
| Criminal proceeds confiscated (EU) | **<2%** of yearly estimated proceeds | [Europol](https://www.europol.europa.eu/crime-areas/criminal-finances-and-money-laundering) |
| STRs further investigated | **~10%** of STRs | [Europol](https://www.europol.europa.eu/media-press/newsroom/news/global-anti-money-laundering-framework-%E2%80%93-europol-report-reveals-poor-success-rate-and-offers-ways-to-improve) |
| Global ML volume as % of GDP | **2-5%** ($2.2-5.5 trillion) | [UNODC](https://www.unodc.org/documents/data-and-analysis/Studies/Illicit-financial-flows-15March.pdf) |

### 3.2 System-Level Detection Rate Estimates

| Aspect | Estimate | Reasoning |
|--------|----------|-----------|
| **Bank TM system recall (rule-based)** | **Estimated 5-20%** of truly illicit transactions | Not directly measured; inferred from the gap between ML volume estimates and detection volumes |
| **System + human combined recall** | **Estimated 10-30%** of illicit actors eventually flagged | Includes employee referrals, law enforcement tips, etc. |
| **Effective end-to-end detection** | **~1-2%** of illicit flows are ultimately intercepted | UNODC/Europol consensus |
| **Criminal groups using ML in EU** | **~70%** of active criminal networks | [Europol 2023](https://www.aa.com.tr/en/europe/almost-70-of-criminal-groups-in-eu-use-money-laundering-europol/2989360) |

### 3.3 Academic ML Model Recall Benchmarks (Research Settings)

| Model / Method | Recall | Dataset | Source |
|----------------|--------|---------|--------|
| LSTM baseline | 90.2% | Simulated | [arXiv:2503.10058](https://arxiv.org/html/2503.10058v1) |
| LSTM-GraphSAGE hybrid | 95.4% accuracy | Simulated | Same source |
| Random Forest | FP reduced to 2.1% | Simulated | [ACM 2024](https://dl.acm.org/doi/10.1145/3704137.3704156) |
| Naive Bayes | Recall 0.81 | Simulated | [Springer](https://link.springer.com/article/10.1007/s11227-023-05708-z) |

**Critical caveat**: Academic benchmarks on simulated data (often 10-17% positive rate) do NOT reflect real-world performance where positive rates are ~0.004%. Real-world recall is unknown and likely much lower.

---

## 4. Precision Benchmarks

### 4.1 Alert-Level Precision

| Metric | Value | Context | Source |
|--------|-------|---------|--------|
| Alert-to-SAR conversion (precision proxy) | **1-5%** | Rule-based systems | Industry consensus |
| Alert-to-SAR conversion | **2.8%** | MBCA mid-size bank study | [Jim Richards](https://www.linkedin.com/pulse/rules-based-monitoring-alert-sar-ratios-false-rates-we-jim-richards) |
| Human referral precision | **40-50%** | Bank employee referrals | Same source |
| AI-enhanced precision | **5-15%** | ML-augmented systems | Vendor estimates |

### 4.2 SAR-to-Prosecution Rate

| Metric | Value | Source |
|--------|-------|--------|
| SARs resulting in any LE follow-up | **~4%** (median) | [Bank Policy Institute 2020](https://bpi.com/the-truth-about-suspicious-activity-reports/) |
| SARs leading to arrest/conviction | **<1%** of filed SARs | [BPI](https://bpi.com/the-truth-about-suspicious-activity-reports/) |
| Cases with SAR involvement (IRS-CI + FBI) | **<0.3%** of FY2023 SARs | [FinCEN FY2023 data](https://www.moneylaunderingnews.com/2024/06/fincen-releases-year-in-review-for-fy-2023-sars-ctrs-and-information-sharing/) |
| IRS-CI prosecutions with BSA filing link | **85.7%** of recommended cases had SAR | [FinCEN](https://www.fincen.gov/reports/sar-stats) |
| BPI estimate: SARs that are false positives of unlawful activity | **90-95%** | [BPI 2020](https://bpi.com/the-truth-about-suspicious-activity-reports/) |

### 4.3 SAR Quality Metrics

| Metric | Context |
|--------|---------|
| **Completeness** | SAR narrative should include who, what, when, where, why |
| **Timeliness** | Must file within 30 calendar days of initial detection |
| **Accuracy** | Subject identification, account information, transaction details |
| **Actionability** | Whether LE can use the SAR to initiate/support investigation |

**Source**: [FFIEC BSA/AML Manual — SAR Quality Guidance](https://bsaaml.ffiec.gov/manual/Appendices/13)

---

## 5. Base Rates — Prevalence of Illicit Actors

### 5.1 Estimates of Illicit Customer Prevalence

| Estimate | Value | Source |
|----------|-------|--------|
| Clients reported for money laundering | **~0.004%** of bank clients | [Nature Scientific Data, synthetic AML benchmark](https://www.nature.com/articles/s41597-023-02569-2) |
| Global ML volume | 2-5% of GDP | [UNODC](https://www.unodc.org/unodc/en/money-laundering/overview.html) |
| ML through traditional banking | ~50% of global ML | [Industry estimates](https://withpersona.com/blog/the-most-mind-blowing-money-laundering-statistics-of-2022) |
| Synthetic dataset positive rate | ~17% (unrealistically high) | [Nature](https://www.nature.com/articles/s41597-023-02569-2) |

### 5.2 Derived Base Rate Calculation

**For a typical US bank:**
- ~325 million US bank accounts
- 2.6 million SARs filed by depository institutions
- SAR filing rate ≈ 0.8% of accounts per year
- But SARs ≠ confirmed illicit → maybe 4-10% of SARs are truly illicit
- **Estimated truly illicit account prevalence: ~0.03-0.08%** (30-80 per 100,000 accounts)

**For a high-risk jurisdiction (Dominican Republic):**
- Higher base rate expected due to:
  - Drug transit corridor (Colombia→DR→US)
  - Cash-intensive economy
  - Informal financial sector
  - Proximity to other high-risk jurisdictions
- **Estimated illicit prevalence: ~0.1-0.5%** (100-500 per 100,000 accounts)
- This is a rough estimate based on jurisdiction risk multipliers

### 5.3 The Class Imbalance Problem

| Metric | Value |
|--------|-------|
| Positive class in real AML data | ~0.004% to 0.1% |
| Positive class in academic datasets | 10-17% (artificially inflated) |
| Imbalance ratio (real world) | 1:1,000 to 1:25,000 |
| Imbalance ratio (academic) | 1:5 to 1:10 |

**Source**: [arXiv:2201.04207 — Fighting Money Laundering with Statistics and Machine Learning](https://arxiv.org/pdf/2201.04207)

---

## 6. FATF Effectiveness Ratings — Dominican Republic

### 6.1 GAFILAT Mutual Evaluation Report (September 2018)

On-site visit: January 15-25, 2018. Assessed under 2012 FATF Recommendations using 2013 Methodology.

| Immediate Outcome | Topic | Rating |
|-------------------|-------|--------|
| IO.1 | ML/TF risk understanding and coordination | **Moderate** |
| IO.2 | International cooperation | **Substantial** |
| IO.3 | AML/CFT supervision | **Moderate** |
| IO.4 | Preventive measures (by private sector) | **Moderate** |
| IO.5 | Legal persons/arrangements (beneficial ownership) | **Moderate** |
| **IO.6** | **Financial intelligence use** | **Moderate** |
| **IO.7** | **ML investigation and prosecution** | **Moderate** |
| IO.8 | Confiscation of proceeds | **Moderate** |
| IO.9 | TF investigation and prosecution | **Substantial** |
| IO.10 | TF prevention and NPO sector | **Moderate** |
| IO.11 | WMD proliferation financing prevention | **Low** |

**Overall: 0 High, 2 Substantial, 8 Moderate, 1 Low**

**Sources**:
- [FATF — DR MER 2018](https://www.fatf-gafi.org/en/publications/Mutualevaluations/Mer-dominican-republic-2018.html)
- [GAFILAT MER PDF](https://www.fatf-gafi.org/content/dam/fatf-gafi/fsrb-mer/GAFILAT-MER-Dominican-Republic-2018.pdf.coredownload.inline.pdf)

### 6.2 Key Findings for IO.6 (Financial Intelligence)

- UAF cooperation with prosecutors (Ministerio Publico) shows higher effectiveness
- Operational use of intelligence reports in investigations is **limited**
- Quality of STR filings from financial sector is better than from DNFBPs
- Banks showed **72% effectiveness** for suspicious transaction reporting
- Non-financial sectors showed only 6-10% effectiveness

**Source**: [FATF MER DR 2018](https://www.fatf-gafi.org/en/publications/Mutualevaluations/Mer-dominican-republic-2018.html)

### 6.3 Key Findings for IO.7 (ML Investigation)

- ML investigations and prosecutions rated **Moderate**
- Risk-based supervision of banking sector is at early stage of implementation
- Sanctions regime needs strengthening
- Limited track record of complex ML prosecutions

### 6.4 Follow-Up Progress (2019)

- Recommendation 18 re-rated from Partially Compliant to Largely Compliant
- Ongoing improvements to AML framework

**Source**: [FATF FUR DR 2019](https://www.fatf-gafi.org/en/publications/mutualevaluations/documents/fur-dominican-republic-2019.html)

### 6.5 Global Context

| Statistic | Value | Source |
|-----------|-------|--------|
| Countries with low/moderate effectiveness in private sector AML | **97%** | [FATF State of Effectiveness Report 2022](https://www.fatf-gafi.org/content/dam/fatf-gafi/reports/Report-on-the-State-of-Effectiveness-Compliance-with-FATF-Standards.pdf.coredownload.pdf) |
| Countries with low/moderate effectiveness in asset recovery | **>80%** | Same source |
| Financial institution supervisors with effective risk-based approach | **17%** | [Napier AI summary](https://www.napier.ai/post/fatf-effectiveness-report-summary) |

---

## 7. Comparable Jurisdiction Data

### 7.1 FATF Effectiveness Ratings Comparison

| Country | IO.6 (Fin. Intel.) | IO.7 (ML Investigation) | Grey List History | Source |
|---------|--------------------|-----------------------|-------------------|--------|
| **Dominican Republic** | Moderate | Moderate | Not currently listed | [GAFILAT MER 2018](https://www.fatf-gafi.org/en/publications/Mutualevaluations/Mer-dominican-republic-2018.html) |
| **Jamaica** | Low-Moderate* | Low-Moderate* | Removed June 2024 | [CFATF MER 2017](https://www.fatf-gafi.org/content/dam/fatf-gafi/fsrb-mer/CFATF-Mutual-Evaluation-Jamaica-2017.pdf.coredownload.inline.pdf) |
| **Panama** | Low-Moderate* | Low* | Grey listed 2019, action plan completed | [GAFILAT MER 2018](https://www.fatf-gafi.org/content/dam/fatf-gafi/fsrb-mer/MER-GAFILAT-Panama-Jan-2018.pdf.coredownload.inline.pdf) |
| **Colombia** | Moderate-Substantial* | Moderate* | Not listed | [GAFILAT MER 2018](https://www.fatf-gafi.org/en/publications/Mutualevaluations/Mer-colombia-2018.html) |
| **Trinidad & Tobago** | Low-Moderate* | Low-Moderate* | Was on grey list, completed action plan | [CFATF evaluation](https://www.fatf-gafi.org/en/countries/global-network/caribbean-financial-action-task-force--cfatf-.html) |

*Note: Ratings marked with asterisk are approximated from available search data; exact ratings should be confirmed from full MER documents.

### 7.2 Regional ML/TF Risk Index (Basel AML Index)

| Country | Basel AML Index Score (2024) | Risk Level |
|---------|------------------------------|------------|
| Haiti | 7.92 | Very High |
| Venezuela | 7.59 | Very High |
| Dominican Republic | ~4.96 (improving from 6.74 in 2016) | Medium-High |
| Panama | High (grey listed) | High |
| Colombia | Medium-High | Medium-High |
| Jamaica | Medium-High (improving) | Medium-High |

**Source**: [Statista ML/TF Risk Index LatAm](https://www.statista.com/statistics/817990/risk-index-money-laundering-terrorist-financing-latin-america/)

### 7.3 Jamaica Key Facts

- Placed under CFATF enhanced follow-up (8+ NC/PC ratings + low/moderate effectiveness on 7+ IOs)
- Removed from FATF grey list in June 2024 after completing action plan
- Introduced Charities regulations and brought microcredit sector under AML/CFT supervision

**Source**: [FATF Jamaica](https://www.fatf-gafi.org/en/publications/Mutualevaluations/Mer-jamaica-2017.html)

### 7.4 Panama Key Facts

- Grey listed by FATF in June 2019 due to strategic AML/CFT deficiencies
- On-site visit approved after action plan completion
- Significant banking sector (~$130B in assets) with offshore component

**Source**: [FATF Panama](https://www.fatf-gafi.org/en/countries/detail/Panama.html)

---

## 8. AI/ML System Improvement Benchmarks

### 8.1 HSBC + Google Cloud AML AI (Flagship Case Study)

| Metric | Value | Source |
|--------|-------|--------|
| Alert volume reduction | **>60%** | [Google Cloud PR](https://www.prnewswire.com/news-releases/google-cloud-launches-ai-powered-anti-money-laundering-product-for-financial-institutions-301856403.html) |
| Suspicious activity detection improvement | **2-4x more** suspicious activity identified | [Google Cloud](https://cloud.google.com/anti-money-laundering-ai) |
| Analyst time savings | **Thousands of hours/month** | [AIINX Case Study](https://aiinx.ai/blog/case-study-how-hsbc-reduced-false-positives-by-60-and-boosted-aml-precision-with-ai/) |
| Transactions monitored | >1 billion/month | Same source |
| Product name | Dynamic Risk Assessment (DRA) | [HSBC/Google](https://www.gobeyond.ai/ai-resources/case-studies/hsbc-ai-google-cloud-fraud-detection) |

### 8.2 Industry-Wide AI/ML Improvements

| Metric | Value | Source |
|--------|-------|--------|
| False positive reduction (AI general) | **50-90%** | [Flagright](https://www.flagright.com/post/ai-and-the-future-of-aml-compliance) |
| UOB false positive reduction | **50%** | [EY](https://www.ey.com/en_se/insights/financial-services/how-ai-is-reshaping-the-future-of-transaction-monitoring) |
| UOB misclassification rate | **<1%** | Same source |
| UOB true positive increase | **5%** | Same source |
| SAR processing time reduction | **30-40%** | Various vendor reports |
| Random Forest FP rate (academic) | **2.1%** | [ACM 2024](https://dl.acm.org/doi/10.1145/3704137.3704156) |

### 8.3 Global AML Compliance Spending

| Metric | Value | Source |
|--------|-------|--------|
| Global AML compliance spending | **~$206 billion/year** | [Flagright](https://www.flagright.com/post/overcoming-the-hidden-costs-of-aml-compliance) |
| AML technology investment (2024 est.) | ~$34.7 billion | [Celent 2024](https://www.fourthline.com/blog/how-much-do-banks-spend-on-compliance) |
| AML operational spending (2024 est.) | ~$155.3 billion | Same source |
| North America AML spending | ~$87 billion | Industry estimates |
| 2023 cost increase reported by institutions | 98% reported increase | [Lucinity](https://lucinity.com/blog/the-real-cost-of-anti-money-laundering-compliance-where-can-banks-cut-expenses-without-increasing-risk) |

---

## 9. Summary: Recommended Targets for DR Retail Bank

### 9.1 Realistic Performance Envelope

Based on all benchmarks gathered, here is the recommended calibration for a retail bank AML system in the Dominican Republic (high-risk jurisdiction):

#### Rule-Based Transaction Monitoring System

| Metric | Conservative Target | Ambitious Target | Industry Baseline | Notes |
|--------|-------------------|-----------------|-------------------|-------|
| **Alert-to-SAR Conversion Rate** | 3-5% | 8-15% | 1-5% | Higher than US baseline due to high-risk jurisdiction |
| **False Positive Rate (alert level)** | 95-97% | 85-92% | 95-99% | Rule-based systems inherently noisy |
| **Recall (detection rate)** | Unknown (~10-20%?) | 30-40% | ~5-20% est. | Cannot be directly measured; aim for scenario coverage |
| **Precision (alert level)** | 3-5% | 8-15% | 1-5% | Equivalent to alert-to-SAR rate |

#### Anomaly Detection (ML) System

| Metric | Conservative Target | Ambitious Target | Industry Baseline | Notes |
|--------|-------------------|-----------------|-------------------|-------|
| **Alert-to-SAR Conversion Rate** | 8-15% | 20-40% | 5-15% (ML systems) | ML should significantly outperform rules |
| **False Positive Reduction vs. Rules** | 40-50% reduction | 60-80% reduction | 50% (UOB), 60% (HSBC) | Well-documented improvement range |
| **Recall Improvement vs. Rules** | +5-10% | +20-50% | 2-4x (HSBC) | Incremental detections rules miss |
| **Precision** | 8-15% | 20-40% | 5-15% | |

#### Combined System (Rules + ML)

| Metric | Realistic Target | Aspirational Target | Notes |
|--------|-----------------|---------------------|-------|
| **Overall Recall** | 15-30% of illicit actors | 30-50% | Combining rules + anomaly detection |
| **Overall Precision (alert level)** | 5-10% | 15-25% | Blended across all alert types |
| **False Positive Rate** | 90-95% | 75-85% | Lower with ML overlay |
| **Alert Volume** | Manageable (50-200 alerts/analyst/month) | Optimized | Capacity-driven constraint |

### 9.2 Base Rate Assumptions for the DR

| Parameter | Low Estimate | Central Estimate | High Estimate |
|-----------|-------------|-----------------|---------------|
| Illicit customer prevalence | 0.05% | 0.1-0.3% | 0.5-1.0% |
| Per 100,000 accounts | 50 | 100-300 | 500-1,000 |
| Illicit transaction prevalence | 0.01% | 0.05-0.1% | 0.5% |

**Rationale**: DR is a high-risk jurisdiction (drug transit, cash-intensive, informal economy), but most customers are legitimate retail/small business. The base rate in a high-risk jurisdiction could be 2-5x that of a typical US bank.

### 9.3 Key Caveats and Honest Limitations

1. **Recall is fundamentally unmeasurable**: No one knows the true denominator of illicit activity. The 1% UNODC seizure estimate is for the global system, not individual banks.

2. **Alert-to-SAR is not precision**: Filing a SAR does not mean the activity was truly illicit — it means it was suspicious enough to report. Many SARs are "defensive" filings. The BPI estimates 90-95% of SARs are false positives of actual criminal activity.

3. **Academic benchmarks are misleading**: Papers showing 90%+ recall operate on datasets with 10-17% positive rates. Real-world positive rates are 0.004-0.1%, making these results non-transferable.

4. **The "good enough" standard is regulatory, not statistical**: Regulators evaluate whether your system is "reasonably designed" — they do not require specific recall/precision numbers. The FFIEC manual focuses on risk coverage, not statistical metrics.

5. **High-risk jurisdiction premium**: A DR bank should expect (and plan for):
   - Higher alert volumes per account than a US/Canadian bank
   - More complex investigation narratives
   - Greater regulatory scrutiny
   - Need for Spanish/English bilingual compliance capability

### 9.4 The Fundamental Tradeoff

```
HIGH RECALL ←————————————→ LOW FALSE POSITIVES
(catch more bad actors)         (fewer wasted investigations)

Current industry: Low recall, very high FP
Target: Moderate recall, moderate FP

The constraint is analyst capacity:
- If you have 10 analysts and 200 alerts/analyst/month = 2,000 alerts/month capacity
- At 3% precision = ~60 SARs/month
- At 10% precision = ~200 SARs/month (same capacity, better targeting)
```

### 9.5 Recommended Reporting Metrics

For the DR retail bank, track and report these KPIs:

| KPI | Formula | Target |
|-----|---------|--------|
| Alert Volume | Total alerts generated per month | Capacity-matched |
| Alert-to-Case Rate | Cases opened / Alerts generated | 10-15% |
| Case-to-SAR Rate | SARs filed / Cases opened | 25-40% |
| Alert-to-SAR Rate | SARs filed / Alerts generated | 3-8% (rules), 10-20% (ML) |
| SAR Filing Timeliness | % filed within regulatory deadline | 100% target |
| Scenario Coverage | # of FATF/Wolfsberg typologies covered | >80% of applicable typologies |
| False Positive Trend | Month-over-month FP rate change | Decreasing |
| Detection Uplift (ML) | Unique detections by ML not caught by rules | Tracked monthly |
| Analyst Productivity | Cases closed per analyst per month | 150-250 |

---

## References (Complete List)

### Regulatory and Government Sources
1. FinCEN SAR Stats — https://www.fincen.gov/reports/sar-stats
2. FinCEN Year in Review FY2024 — https://www.fincen.gov/system/files/2025-08/FinCEN-Infographic-Public-2025-508.pdf
3. FINTRAC STR Reporting — https://fintrac-canafe.canada.ca/guidance-directives/transaction-operation/str-dod/str-dod-eng
4. FDIC Statistics at a Glance — https://www.fdic.gov/quarterly-banking-profile/fdic-statistics-glance
5. FDIC Household Survey 2023 — https://www.fdic.gov/news/press-releases/2024/fdic-survey-finds-96-percent-us-households-were-banked-2023
6. FFIEC BSA/AML Manual — https://bsaaml.ffiec.gov/manual/AssessingComplianceWithBSARegulatoryRequirements/04
7. US Treasury National ML Risk Assessment 2024 — https://home.treasury.gov/system/files/136/2024-National-Money-Laundering-Risk-Assessment.pdf
8. UAF Dominican Republic — https://www.uaf.gob.do/
9. FRED: DR Bank Accounts — https://fred.stlouisfed.org/series/DDAI01DOA642NWDB

### FATF/GAFILAT Sources
10. FATF MER Dominican Republic 2018 — https://www.fatf-gafi.org/en/publications/Mutualevaluations/Mer-dominican-republic-2018.html
11. FATF FUR Dominican Republic 2019 — https://www.fatf-gafi.org/en/publications/mutualevaluations/documents/fur-dominican-republic-2019.html
12. FATF Consolidated Assessment Ratings — https://www.fatf-gafi.org/en/publications/Mutualevaluations/Assessment-ratings.html
13. FATF State of Effectiveness Report 2022 — https://www.fatf-gafi.org/content/dam/fatf-gafi/reports/Report-on-the-State-of-Effectiveness-Compliance-with-FATF-Standards.pdf.coredownload.pdf
14. CFATF Jamaica MER 2017 — https://www.fatf-gafi.org/content/dam/fatf-gafi/fsrb-mer/CFATF-Mutual-Evaluation-Jamaica-2017.pdf.coredownload.inline.pdf
15. GAFILAT Panama MER 2018 — https://www.fatf-gafi.org/content/dam/fatf-gafi/fsrb-mer/MER-GAFILAT-Panama-Jan-2018.pdf.coredownload.inline.pdf
16. GAFILAT Colombia MER 2018 — https://www.fatf-gafi.org/en/publications/Mutualevaluations/Mer-colombia-2018.html

### International Organizations
17. UNODC Illicit Financial Flows — https://www.unodc.org/documents/data-and-analysis/Studies/Illicit-financial-flows-15March.pdf
18. UNODC Money Laundering Overview — https://www.unodc.org/unodc/en/money-laundering/overview.html
19. Europol Criminal Finances — https://www.europol.europa.eu/crime-areas/criminal-finances-and-money-laundering
20. Europol AML Framework Report — https://www.europol.europa.eu/media-press/newsroom/news/global-anti-money-laundering-framework-%E2%80%93-europol-report-reveals-poor-success-rate-and-offers-ways-to-improve

### Industry and Consulting
21. Bank Policy Institute — SAR Truth — https://bpi.com/the-truth-about-suspicious-activity-reports/
22. ABA Banking Journal (FinCEN) — https://bankingjournal.aba.com/2025/06/fincen-releases-figures-on-bsa-filings/
23. Jim Richards — Alert-to-SAR Analysis — https://www.linkedin.com/pulse/rules-based-monitoring-alert-sar-ratios-false-rates-we-jim-richards
24. NICE Actimize SAR Stats 2024 — https://www.niceactimize.com/blog/fraud-prevention-insights-from-unpacking-the-2024-fincen-sar-stats
25. Google Cloud AML AI — https://cloud.google.com/anti-money-laundering-ai
26. HSBC AML AI Case Study — https://aiinx.ai/blog/case-study-how-hsbc-reduced-false-positives-by-60-and-boosted-aml-precision-with-ai/

### Academic Sources
27. Nature: Synthetic AML Benchmark Dataset — https://www.nature.com/articles/s41597-023-02569-2
28. arXiv: Fighting ML with Statistics — https://arxiv.org/pdf/2201.04207
29. arXiv: Deep Learning for AML — https://arxiv.org/html/2503.10058v1
30. ACM: ML for AML False Positive Reduction — https://dl.acm.org/doi/10.1145/3704137.3704156
31. Springer: Automatic Suppression of FP in AML — https://link.springer.com/article/10.1007/s11227-023-05708-z

### Vendor / Research Firms
32. Flagright — FP in Transaction Monitoring — https://www.flagright.com/post/understanding-false-positives-in-transaction-monitoring
33. DataRobot AML Alert Scoring — https://docs.datarobot.com/en/docs/get-started/gs-dr5/biz-accelerators/money-launder.html
34. AML Watcher — FP Management — https://amlwatcher.com/blog/how-to-manage-healthy-aml-false-positive-in-2024/
35. DataVisor — FP in AML — https://www.datavisor.com/blog/guest-post-end-the-false-positive-alerts-plague-in-anti-money-laundering-aml-systems/
36. Napier AI — FATF Effectiveness Summary — https://www.napier.ai/post/fatf-effectiveness-report-summary
37. Trade.gov — DR Financial Services — https://www.trade.gov/country-commercial-guides/dominican-republic-financial-services
38. Sanction Scanner — DR AML — https://www.sanctionscanner.com/aml-guide/anti-money-laundering-aml-in-dominican-republic-604
39. LegalJobs — ML Statistics — https://legaljobs.io/blog/money-laundering-statistics/
