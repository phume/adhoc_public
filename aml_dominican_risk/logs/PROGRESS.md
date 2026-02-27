# Progress Log

## 2026-02-24 — STR Fermi Estimation

- **Task:** Fermi estimation of illicit actors banking at Scotiabank DR
- **Commit:** a9c12a4
- **Files created:**
  - `result_20260224_STR_Estimation.md` — main deliverable
  - `reference/AML_Performance_Benchmarks_Industry_Statistics.md` — AML benchmark research
  - `plans/20260224_Plan_STR_Estimation.md` — frozen plan
  - `logs/PROGRESS.md` — this file
- **Checks:** Content review passed; all sanity checks passed (5/5)
- **Next:** Human review of estimation; potential model design work

## 2026-02-24 — Geolocation Behavioral Typologies

- **Task:** Add composite geolocation typologies and geographic features to master document
- **Commit:** 90c1a05
- **Files modified:**
  - `DR_AML_Risk_Assessment_Master.md` — 10 new typologies (rows 61-70), 8 new features (Section 5.3), updated counts
- **Checks:** Verified row format matches existing 6-column schema; feature naming follows snake_case convention; all counts updated (88→96 features, 60→70 typologies)
- **Next:** Human review

## 2026-02-24 — Slide 6 Speaker Notes (v2.3–v2.7)

- **Task:** Create and iteratively refine detailed speaker notes for STR Fermi estimation Slide 6
- **Commits:**
  - `0e4598a` v2.3 — Initial speaker notes
  - `0d40cd9` v2.4 — Full arithmetic chains for every number
  - `30031b0` v2.5 — Updated with 2024 data sources, fixed outdated figures
  - `01850be` v2.6 — Tagged every number [S]ourced/[A]ssumed; fixed 65% banking penetration error in main doc
  - `ae3482c` v2.7 — Converted to numbered source references (S1-S43) with Source Appendix
- **Files modified:**
  - `result_20260224_STR_Estimation_Slide6_Notes.md` — primary deliverable (all versions)
  - `result_20260224_STR_Estimation.md` — banking penetration fix (65%→51-55%)
- **Key corrections:** Banking penetration 65%→51-55%, cambios 2000→41, lawyers 25K→73K, accountants 10K→5,358, DNCD 3K→4,200, drug arrests 3.8K→49K
- **Checks:** 43 sources mapped; no orphan references; all numbers tagged
- **Next:** Human review

## 2026-02-26 — Venezuela & Mexico AML Risk Assessment

- **Task:** Research VZ and MEX geopolitical AML risks for Scotiabank DR (AML Chief Officer / Chief Model Developer perspective)
- **Commit:** a69708f
- **Files created:**
  - `reference/VZ_MEX_AML_Risk_Assessment_20260226.md` — main deliverable (592 lines)
- **Key findings:**
  - VZ: Maduro captured (Jan 2026), $700M assets seized (incl. Cap Cana DR mansion), 80% PDVSA revenue in USDT, SDN list expanding at unprecedented pace
  - MEX: Both Sinaloa (Zambada guilty plea) and CJNG (El Mencho killed Feb 22) decapitated simultaneously; balloon effect confirmed (DR seizures 5x since 2019); 8 cartels designated FTOs
  - Combined risk matrix: 15 factors assessed; 8 rule-based model updates and 10 anomaly detection features proposed
  - 50 sourced references (V1-V27, M1-M23)
- **Checks:** Content review passed; all sources web-verified
- **Next:** Human review
