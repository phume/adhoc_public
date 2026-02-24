# Plan: Fermi Estimation — Illicit Actors Banking at Scotiabank DR

**Date:** 2026-02-24
**Status:** EXECUTED

## Goal
Estimate the number of STRs, drug traffickers, and illicit actors who plausibly bank with Scotiabank DR to calibrate False Negative, Recall, and Precision targets.

## Approach
1. Research completed (3 parallel agents): DR banking market, crime stats, AML benchmarks
2. Write Fermi estimation with explicit assumptions into `result_20260224_STR_Estimation.md`
3. Break down by risk category (DTOs, street dealers, fentanyl, mules, human trafficking, ML professionals)
4. Derive expected STR volume, recall, and precision targets

## Output
- Result file: `result_20260224_STR_Estimation.md`
- Reference file: `reference/AML_Performance_Benchmarks_Industry_Statistics.md`

## Key Findings
- ~1,250 illicit actors likely bank at Scotiabank DR (mid-estimate, 0.25% of clients)
- ~450 are "detectable" through transaction monitoring (0.09% base rate)
- Recommended STR target: 250-400/year (~20-33/month)
- Year 1 recall target: 10-15%; Year 2: 20-30%
- Alert-to-STR precision target: 5-10% (with ML enhancement)
- AML ops team sizing: 3-5 FTE
