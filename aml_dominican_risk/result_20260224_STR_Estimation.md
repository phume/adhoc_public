# Fermi Estimation: Illicit Actors Banking at Scotiabank DR

**Date:** 2026-02-24
**Purpose:** Estimate STR volumes, illicit actor prevalence, and calibrate Recall/Precision/FPR targets for AML model
**Method:** Bottom-up Fermi estimation with explicit assumptions and range estimates

---

## Table of Contents

1. [Key Assumptions](#1-key-assumptions)
2. [Scotiabank DR Customer Base](#2-scotiabank-dr-customer-base)
3. [Illicit Actor Estimates by Category](#3-illicit-actor-estimates-by-category)
4. [Banking Penetration of Illicit Actors](#4-banking-penetration-of-illicit-actors)
5. [Expected Illicit Actors at Scotiabank DR](#5-expected-illicit-actors-at-scotiabank-dr)
6. [Expected STR Volume](#6-expected-str-volume)
7. [Model Performance Calibration Targets](#7-model-performance-calibration-targets)
8. [Sanity Checks](#8-sanity-checks)
9. [Key Uncertainties and Limitations](#9-key-uncertainties-and-limitations)
10. [Sources](#10-sources)

---

## 1. Key Assumptions

All assumptions are numbered for traceability.

### Market Assumptions
| # | Assumption | Value | Source / Basis |
|---|-----------|-------|---------------|
| A1 | DR population | 11.5M | Worldometers 2025 |
| A2 | DR adult population (15+) | ~8.4M | 73.4% of total population |
| A3 | Banking penetration (adults) | ~51-55% | World Bank Global Findex 2021: 51.3%; central bank/industry estimates: ~55%. Note: 65% is the DR's 2030 ENIF target, not current rate. |
| A4 | Banked adults in DR | ~4.3-4.6M | A2 × A3 (8.4M × 51-55%) |
| A5 | Total household deposit accounts | ~7.3M | IMF FAS 2024 (861.3 per 1,000 adults) |
| A6 | Commercial banks in DR | 16-18 | SIB / IMF |
| A7 | Total financial entities (regulated) | 49 | US Trade.gov |
| A8 | Scotiabank DR market share (assets) | 4-7% | $2.77B of ~$68B system; 4th largest bank |
| A9 | Scotiabank DR retail clients (est.) | 400,000-600,000 | Proportional to market share vs. BanReservas (3M+, ~32%) and Banco Popular (2M+, ~20%) |
| A10 | Scotiabank DR branches | 46-58 | Scotiabank.do |
| A11 | Scotiabank share of banked adults | ~11-12% | Mid-estimate: 500K / ~4.5M |

### Economy Assumptions
| # | Assumption | Value | Source / Basis |
|---|-----------|-------|---------------|
| A12 | DR GDP (2024) | $124.3B | World Bank |
| A13 | Shadow/informal economy (% GDP) | ~34% | World Economics |
| A14 | Informal employment | 54.7% | Statista 2024 |
| A15 | Total remittances (2024) | $10.76B | BCRD official |
| A16 | Remittance transactions/year | ~30M | Inter-American Dialogue |
| A17 | Cash-received remittances | >75% (~$8B+) | Inter-American Dialogue |
| A18 | Total MSMEs (formal + informal) | ~404,000 | BCRD/MICM survey 2022-23 |
| A19 | Formally registered MSMEs | ~59,800 (14.8%) | Diario Libre |

### AML System Assumptions
| # | Assumption | Value | Source / Basis |
|---|-----------|-------|---------------|
| A20 | UAF intelligence reports produced/year | ~520-530 | UAF Memoria Institucional 2023 |
| A21 | UAF reports forwarded to prosecutors/year | ~32-55 | UAF 2022-2023 reports |
| A22 | Estimated incoming ROS (STRs) to UAF/year | 2,000-5,000 | Estimate; not publicly reported |
| A23 | Global ML detection rate | ~1% of criminal proceeds seized | UNODC |
| A24 | Rule-based alert-to-SAR conversion | 1-5% | Industry benchmark (PwC, vendors) |
| A25 | ML-enhanced alert-to-SAR conversion | 5-15% | HSBC/Google Cloud, UOB case studies |

---

## 2. Scotiabank DR Customer Base

**Central estimate: ~500,000 retail clients**

| Scenario | Clients | Basis |
|----------|---------|-------|
| Low | 350,000 | Conservative 4% of banked adults + multi-banking adjustment |
| Mid | 500,000 | 7% market share × ~7.3M accounts, deduplicated |
| High | 600,000 | 10% market share claim (post-Progreso merger 2020) |

**Small business clients (subset):**

| Scenario | SME Clients | Basis |
|----------|-------------|-------|
| Low | 3,000 | Only formally registered MSMEs banking with Scotia (~5% of 59,800) |
| Mid | 6,000 | ~10% of registered MSMEs |
| High | 12,000 | Including semi-formal businesses |

---

## 3. Illicit Actor Estimates by Category

Estimates of **total** illicit actors in DR (not just those banking at Scotiabank).

### 3.1 Drug Trafficking Organizations (DTOs) — International Level

Individuals involved in international cocaine/heroin transit through DR.

| Tier | Low | Mid | High | Basis |
|------|-----|-----|------|-------|
| DTO leadership/principals | 50 | 100 | 200 | Treasury Kingpin designees, top-tier arrests |
| Mid-level transporters/operatives | 1,000 | 3,000 | 5,000 | Maritime crews (~3 go-fast boats/week), port workers, logistics |
| Facilitators (corrupt officials, lawyers, brokers) | 500 | 1,500 | 3,000 | State-embedded actors per OC Index |
| **Subtotal** | **1,550** | **4,600** | **8,200** | |

Context: ~120 tons cocaine transit Hispaniola annually (DNCD). 37.7 tons seized in 2024 (record). ~25-31% interdiction rate.

### 3.2 Street-Level Drug Dealers (Domestic Market)

| Tier | Low | Mid | High | Basis |
|------|-----|-----|------|-------|
| Full-time dealers | 5,000 | 15,000 | 30,000 | Major cities each have hundreds of "puntos" |
| Part-time/occasional sellers | 10,000 | 30,000 | 60,000 | Harvard ReVista: drug selling as "part-time job" in informal economy |
| **Subtotal** | **15,000** | **45,000** | **90,000** | |

Note: Street dealers are the largest category but least likely to bank formally. Many operate entirely in cash within the informal economy.

### 3.3 Fentanyl/Heroin Distribution Network (US-DR Nexus)

Dominican nationals involved in fentanyl/heroin distribution in US Northeast, with DR financial ties.

| Tier | Low | Mid | High | Basis |
|------|-----|-----|------|-------|
| US-based mid-level+ distributors | 500 | 1,500 | 3,000 | DEA: Dominican TCOs "dominant retail distributors" in NE US |
| US-based street-level dealers | 2,000 | 5,000 | 10,000 | DOJ HIDTA assessments |
| DR-based supply/money operatives | 200 | 500 | 1,000 | Source-side logistics |
| **Subtotal** | **2,700** | **7,000** | **14,000** | |

**Banking relevance:** DR-based operatives (200-1,000) and US-based actors sending money back to DR are the most relevant to Scotiabank DR. Remittance flows from US to DR accounts are the primary channel.

### 3.4 Money Mules

| Tier | Low | Mid | High | Basis |
|------|-----|-----|------|-------|
| US-side mules (Dominican nationals) | 500 | 2,000 | 5,000 | Multiple cells across NJ/NY/FL |
| DR-side mules (receiving/distributing) | 300 | 1,000 | 3,000 | Domestic cash distribution, cambios, real estate |
| Complicit remittance/exchange staff | 100 | 300 | 600 | FinCEN specifically targeted DR remitters |
| **Subtotal** | **900** | **3,300** | **8,600** | |

**Banking relevance:** HIGH. Money mules by definition use bank accounts. DR-side mules (300-3,000) are prime candidates for Scotiabank accounts.

### 3.5 Human Trafficking Networks

| Tier | Low | Mid | High | Basis |
|------|-----|-----|------|-------|
| Network operators | 100 | 300 | 600 | 229 investigations opened (2023 TIP Report) |
| Facilitators (recruiters, transporters, forgers) | 300 | 800 | 1,500 | Multiple facilitators per ring |
| **Subtotal** | **400** | **1,100** | **2,100** | |

TIP tier: Tier 2 (2025). 40 prosecuted, 20 convicted in 2023.

### 3.6 Money Laundering Professionals

| Tier | Low | Mid | High | Basis |
|------|-----|-----|------|-------|
| Lawyers/accountants/real estate agents in ML | 200 | 500 | 1,000 | Weak DNFBP supervision; real estate is primary laundering vehicle |
| **Subtotal** | **200** | **500** | **1,000** | |

**Banking relevance:** VERY HIGH. ML professionals operate through formal banking. Near-100% banking penetration.

### 3.7 Corrupt Officials / PEPs

| Tier | Low | Mid | High | Basis |
|------|-----|-----|------|-------|
| PEPs facilitating organized crime | 100 | 300 | 500 | OC Index: military/police participation in trafficking |
| Corrupt law enforcement | 200 | 500 | 1,000 | Documented police purges |
| Corrupt administrative officials (customs, ports) | 100 | 300 | 500 | Port-based trafficking requires insiders |
| **Subtotal** | **400** | **1,100** | **2,000** | |

**Banking relevance:** HIGH. Officials bank formally and receive legitimate salaries alongside illicit income.

### Summary: Total Illicit Actors in DR

| Category | Low | Mid | High |
|----------|-----|-----|------|
| DTOs (international) | 1,550 | 4,600 | 8,200 |
| Street dealers (domestic) | 15,000 | 45,000 | 90,000 |
| Fentanyl/heroin network (US-DR) | 2,700 | 7,000 | 14,000 |
| Money mules | 900 | 3,300 | 8,600 |
| Human trafficking | 400 | 1,100 | 2,100 |
| ML professionals | 200 | 500 | 1,000 |
| Corrupt officials/PEPs | 400 | 1,100 | 2,000 |
| **Total (before dedup)** | **21,150** | **62,600** | **125,900** |
| **Total (deduplicated ~30%)** | **~15,000** | **~44,000** | **~88,000** |

As % of adult population (8.4M): **0.18% / 0.52% / 1.05%**

---

## 4. Banking Penetration of Illicit Actors

Not all illicit actors bank formally. Banking penetration varies dramatically by category.

| Category | Est. Banking Rate | Reasoning |
|----------|------------------|-----------|
| DTO leadership | 90-100% | Need formal accounts for legitimate front businesses |
| DTO mid-level operatives | 50-70% | Mix of formal/informal; many use cash |
| Street dealers (full-time) | 30-50% | Many are unbanked; operate in cash economy |
| Street dealers (part-time) | 15-30% | Informal economy; below national ~51-55% banking rate |
| Fentanyl network (DR-based) | 60-80% | Need accounts for receiving US remittances |
| Money mules (DR-side) | 95-100% | Bank accounts are their operational tool |
| Human traffickers | 50-70% | Mix of formal/informal operations |
| ML professionals | 95-100% | Lawyers/accountants have formal financial lives |
| Corrupt officials | 95-100% | Salary deposited to bank accounts |

### Estimated Banked Illicit Actors in DR

| Category | Low | Mid | High | Banking Rate Applied |
|----------|-----|-----|------|---------------------|
| DTOs (international) | 850 | 2,800 | 5,700 | 55-70% |
| Street dealers | 3,400 | 11,300 | 27,000 | 20-30% |
| Fentanyl network (DR-based only) | 140 | 350 | 700 | 70% |
| Money mules (DR-side) | 285 | 950 | 2,850 | 95% |
| Human trafficking | 220 | 660 | 1,260 | 55-60% |
| ML professionals | 190 | 475 | 950 | 95% |
| Corrupt officials | 380 | 1,045 | 1,900 | 95% |
| **Total banked illicit actors** | **~5,500** | **~17,600** | **~40,400** |

As % of banked population (~4.5M): **0.12% / 0.39% / 0.90%**

---

## 5. Expected Illicit Actors at Scotiabank DR

Applying Scotiabank's estimated market share (~11-12% of banked adults, or ~7% of total accounts) to the banked illicit actor pool. We assume illicit actors distribute across banks roughly proportional to market share, with some adjustment.

**Key assumption (A26):** Illicit actors are not randomly distributed across banks. Larger banks with more branches, ATMs, and remittance services are disproportionately attractive. However, Scotiabank is 4th largest, not dominant. We apply a factor of 1.0x (proportional) as the base case.

| Category | Low | Mid | High | Calculation |
|----------|-----|-----|------|-------------|
| DTOs | 60 | 200 | 400 | Banked × 7% share |
| Street dealers | 240 | 800 | 1,900 | Banked × 7% share |
| Fentanyl (DR-based) | 10 | 25 | 50 | Banked × 7% |
| Money mules | 20 | 70 | 200 | Banked × 7% |
| Human trafficking | 15 | 45 | 90 | Banked × 7% |
| ML professionals | 13 | 35 | 65 | Banked × 7% |
| Corrupt officials | 27 | 75 | 135 | Banked × 7% |
| **Total illicit actors at Scotiabank** | **~385** | **~1,250** | **~2,840** |

As % of Scotiabank retail clients (500K mid): **0.08% / 0.25% / 0.57%**

### Breakdown: Who Matters Most for AML Detection?

Not all illicit actors generate detectable transaction patterns. Prioritize by **detectability** (anomalous banking behavior):

| Priority | Category | Count (Mid) | Detectability | Why |
|----------|----------|-------------|---------------|-----|
| 1 | Money mules | 70 | Very High | Rapid in/out flows, multiple remittances, structuring |
| 2 | ML professionals | 35 | High | Unusual transaction patterns for stated occupation |
| 3 | DTOs (mid-level+) | 200 | High | Large cash deposits, business front anomalies |
| 4 | Corrupt officials | 75 | Medium-High | Wealth inconsistent with salary |
| 5 | Fentanyl network | 25 | Medium | Remittance patterns from US |
| 6 | Human trafficking | 45 | Medium | Cash businesses, cross-border flows |
| 7 | Street dealers | 800 | Low | Small amounts, blend with informal economy |
| **Total "detectable"** (Priority 1-6) | | **~450** | | Excluding most street dealers |

**Key insight:** The ~450 "detectable" illicit actors (mid-estimate) among ~500,000 clients gives a **base rate of ~0.09%**, or roughly **1 in 1,100 clients**. This is consistent with the industry benchmark of 1:1,000 to 1:25,000 from academic literature.

---

## 6. Expected STR Volume

### 6.1 Top-Down Estimate (From National UAF Data)

| Metric | Value | Source |
|--------|-------|--------|
| UAF incoming ROS/year (est.) | 2,000-5,000 | Estimate (not publicly reported) |
| DR financial entities | 49 | SIB |
| Scotiabank share of system STRs | ~5-8% | Proportional to market share |
| **Scotiabank expected STRs/year** | **100-400** | 3,500 × 7% = ~245 (mid) |

### 6.2 Bottom-Up Estimate (From Illicit Actor Count)

| Parameter | Low | Mid | High |
|-----------|-----|-----|------|
| Detectable illicit actors at Scotia | 150 | 450 | 1,000 |
| Estimated system recall (detection rate) | 5% | 15% | 30% |
| True positives (illicit actors flagged) | 8 | 68 | 300 |
| False positive multiplier (alerts per TP) | 20x | 15x | 8x |
| Total alerts generated | 160 | 1,020 | 2,400 |
| Alert-to-STR conversion | 30% | 40% | 50% |
| **STRs filed/year** | **48** | **408** | **1,200** |

### 6.3 Benchmark Comparison

| Benchmark | STR Rate | Applied to Scotia (500K clients) |
|-----------|----------|----------------------------------|
| US banks: ~8 SARs/1,000 accounts/year | 8‰ | 4,000 (too high — US is over-filing) |
| Canada: ~7 STRs/1,000 accounts/year | 7‰ | 3,500 (too high — Canada is over-filing) |
| High-risk LatAm (adjusted): ~0.5-1.0/1,000 | 0.5-1‰ | 250-500 |
| DR system (est.): ~0.3-0.7/1,000 | 0.3-0.7‰ | 150-350 |

### 6.4 Consolidated STR Estimate

| Scenario | STRs/Year | STRs/Month | Basis |
|----------|-----------|------------|-------|
| Low | 100 | ~8 | Conservative; current weak detection |
| **Mid** | **250-400** | **~20-33** | Balanced; improved detection with new system |
| High | 800-1,200 | ~65-100 | Aggressive; US-style filing posture |

**Recommended planning target: 250-400 STRs/year (~20-33/month)**

This reflects a bank that is materially improving its AML program post-acquisition, but not yet at US/Canadian filing intensity.

---

## 7. Model Performance Calibration Targets

### 7.1 The Base Rate Problem

| Metric | Value |
|--------|-------|
| Total clients | ~500,000 |
| Estimated illicit actors (mid) | ~1,250 |
| Estimated detectable illicit actors (mid) | ~450 |
| **Base rate (all illicit)** | **0.25%** (1 in 400) |
| **Base rate (detectable)** | **0.09%** (1 in 1,100) |
| Industry benchmark | 0.004% - 0.3% |

DR is a high-risk jurisdiction, so base rate toward the higher end of industry range is expected.

### 7.2 Recall Targets

Recall = (Illicit actors detected) / (Total illicit actors present)

| Context | Recall | Basis |
|---------|--------|-------|
| Current global banking average (est.) | 1-5% | UNODC: only ~1% of ML proceeds seized |
| Rule-based systems (typical) | 5-15% | Industry estimates |
| ML-enhanced systems | 15-30% | HSBC/Google Cloud: 2-4x improvement |
| Regulatory expectation ("reasonably designed") | N/A | No specific % required |
| **Recommended target** | | |
| Year 1 (rule-based launch) | **10-15%** | Detect ~45-70 of ~450 detectable actors |
| Year 2 (ML model added) | **20-30%** | Detect ~90-135 of ~450 detectable actors |
| Aspirational (Year 3+) | **30-40%** | Best-in-class for high-risk jurisdiction |

**Honest caveat:** Recall is fundamentally unmeasurable in AML. We never know the true denominator. These targets are Fermi-calibrated, not precisely measurable. Proxy metrics (STR volume trends, case referral rates, law enforcement feedback) must be used instead.

### 7.3 Precision Targets

Precision = (True illicit actors flagged) / (All actors flagged)

| Level | Metric | Current Benchmark | Target |
|-------|--------|-------------------|--------|
| Alert level | Alert-to-investigation rate | 1-5% (rules) | 5-15% (with ML) |
| Investigation level | Investigation-to-STR rate | 20-40% | 30-50% |
| STR level | STR-to-prosecution rate | ~4% (US data) | Not bank-controllable |
| **Overall alert-to-STR** | | **1-5%** | **5-15%** |

**Translation for Scotiabank DR:**

| Scenario | Alerts/Year | STRs Filed | Alert-to-STR | True Positives (est.) |
|----------|-------------|------------|--------------|----------------------|
| Current (rules only) | 10,000-20,000 | 100-200 | 1-2% | 15-40 |
| Target (rules + ML) | 5,000-10,000 | 250-400 | 5-8% | 50-100 |
| Aspirational (mature ML) | 3,000-6,000 | 300-500 | 8-15% | 80-150 |

### 7.4 False Positive Rate Targets

| System | FPR Benchmark | Target |
|--------|--------------|--------|
| Rule-based (legacy) | 95-99% | < 95% |
| Rule-based (well-tuned) | 90-95% | < 92% |
| ML-enhanced (Year 1) | 85-92% | < 90% |
| ML-enhanced (mature) | 80-85% | < 85% |
| Human referral channel | 50-60% | < 55% |

### 7.5 Summary: Recommended Calibration Targets

| Metric | Year 1 Target | Year 2 Target | Year 3+ Aspirational |
|--------|---------------|---------------|---------------------|
| **STRs filed/year** | 150-250 | 250-400 | 400-600 |
| **Recall (est.)** | 10-15% | 20-30% | 30-40% |
| **Alert-to-STR (precision proxy)** | 3-5% | 5-10% | 10-15% |
| **FPR (alert level)** | < 95% | < 90% | < 85% |
| **Alerts/month** | 800-1,500 | 500-1,000 | 300-600 |
| **Investigations/month** | 30-60 | 40-80 | 50-100 |

---

## 8. Sanity Checks

### Check 1: Illicit Actor Prevalence vs. Industry Benchmarks
- Our mid-estimate: 0.25% of clients are illicit = **within range** of industry 0.004%-0.3% (high end, appropriate for high-risk jurisdiction)
- Our detectable estimate: 0.09% = **within range**, consistent with 1:1,000 to 1:25,000 class imbalance in literature

### Check 2: STR Volume vs. Comparable Banks
- Mid-estimate: 250-400 STRs/year from 500K clients = **0.5-0.8 per 1,000 clients**
- US banks file ~8 per 1,000 (much higher due to regulatory posture)
- LatAm banks: 0.3-1.0 per 1,000 (our estimate falls within this)
- **PASS** — reasonable for a DR bank improving its program

### Check 3: Recall Plausibility
- Mid-estimate Year 2: detect 90-135 of ~450 detectable actors = **20-30% recall**
- Industry context: HSBC+Google achieved 2-4x improvement → from ~10% to ~20-40% is plausible
- UNODC 1% refers to proceeds seizure, not detection at bank level; bank-level detection is higher
- **PASS** — ambitious but achievable

### Check 4: STR-to-UAF Contribution
- If Scotiabank files 300 STRs/year, and total system files ~3,500, that's ~8.5% of national volume
- Scotiabank has ~7% market share → filing slightly above market share is expected for a bank with enhanced monitoring
- **PASS** — proportionate

### Check 5: Investigator Workload
- 400 STRs/year ÷ 12 months = ~33 STRs/month
- If each STR requires 4-8 hours of investigation = 130-260 analyst-hours/month
- Requires ~1-2 FTE investigators (at 160 hours/month)
- Plus alert triage: ~800 alerts/month × 15 min = ~200 hours/month = ~1.3 FTE
- **Total AML ops team needed: 3-5 FTE** — reasonable for a bank this size
- **PASS**

---

## 9. Key Uncertainties and Limitations

### High-Impact Uncertainties (could shift estimates by 2x+)

1. **Street dealer banking rate**: If more street dealers bank formally than assumed (e.g., 50% instead of 25%), the base rate doubles. However, their transactions are typically small and hard to detect.

2. **Money mule count**: Money mules are the most operationally relevant category. If the DR-side mule ecosystem is larger than estimated (e.g., 5,000+ vs. 1,000 mid), STR targets should increase.

3. **Scotiabank's actual market share**: The 7% estimate is a Fermi approximation. The true client count could range from 350K to 600K, shifting all per-client rates.

4. **UAF incoming STR volume**: The DR UAF does not publicly disclose total incoming ROS. Our estimate of 2,000-5,000 could be off by 2x in either direction.

### Known Limitations

- **Recall is unmeasurable**: No bank knows how many illicit actors it fails to detect. Targets are Fermi-calibrated benchmarks, not measurable KPIs.

- **Overlap between categories**: Many actors participate in multiple illicit activities (e.g., a DTO operative who is also a money mule). Our 30% deduplication factor is a rough estimate.

- **US-based actors**: The fentanyl network (2,700-14,000 people) is mostly US-based. Only their DR financial footprint (remittances, property, family accounts) is relevant to Scotiabank DR.

- **Temporal dynamics**: Crime networks grow and shrink. The 120-ton cocaine transit figure may be outdated. Fentanyl involvement is rapidly increasing.

- **Detection ≠ filing**: Not all detected suspicious activity results in STRs. Defensive filing practices vary by bank culture and regulatory pressure.

---

## 10. Sources

### DR Banking & Economy
- IMF Financial Access Survey (2024) via FRED
- World Bank Global Findex 2024
- BCRD (Central Bank of DR) — remittance data
- Inter-American Dialogue — remittance market assessment
- BCRD/MICM ENMIPYMES Survey 2022-2023 — MSME data
- World Economics — shadow economy estimates
- US Trade.gov — DR financial services guide

### Crime & Illicit Activity
- US State Department INCSR reports (2023-2025)
- DEA National Drug Threat Assessment 2024
- DEA press releases — Dominican national fentanyl prosecutions
- InSight Crime — DR cocaine seizure records and investigations
- DNCD (Vice Admiral Pimental) — 120-ton transit estimate
- US DOJ HIDTA assessments — Dominican TCO structure
- US Treasury Kingpin Act designations
- TIP Report 2024-2025 — Dominican Republic
- Global Organized Crime Index 2023
- FinCEN — crackdown on DR remittances
- Harvard ReVista — "Organized and Disorganized Crime" (academic)
- Transparency International CPI 2024

### AML Benchmarks
- FinCEN SAR Statistics (FY2024) — US filing volumes
- FINTRAC Annual Report (FY2023-24) — Canada filing volumes
- FATF Mutual Evaluation Report — Dominican Republic (2018)
- HSBC + Google Cloud — AI/ML improvement case study
- UOB — false positive reduction case study
- PwC Global Economic Crime Survey — false positive rates
- UNODC — global ML detection estimates
- Europol — STR investigation and confiscation rates
- BPI (2020) — SAR quality and prosecution rates
- Nature Scientific Data — ML client prevalence in banking

---

*This document was prepared as an internal calibration exercise. All estimates are Fermi approximations with explicitly stated assumptions. They should be updated as better data becomes available, particularly once Scotiabank DR's actual client count and transaction volumes are known.*
