# Venezuela & Mexico AML Risk Assessment — Scotiabank Dominican Republic

**Date:** 2026-02-26
**Perspective:** AML Chief Officer & AML Chief Model Developer, Scotiabank DR
**Purpose:** Geopolitical risk update — how recent developments in Venezuela and Mexico affect AML risk posture for Scotiabank's DR retail banking operations

---

## Table of Contents

1. [Executive Summary](#1-executive-summary)
2. [PART A: Venezuela (VZ)](#part-a-venezuela-vz)
   - [A1. US Sanctions Landscape — Extreme Flux](#a1-us-sanctions-landscape--extreme-flux)
   - [A2. Venezuela-DR Drug Trafficking Corridor](#a2-venezuela-dr-drug-trafficking-corridor)
   - [A3. Venezuelan Migration & Remittance Risk](#a3-venezuelan-migration--remittance-risk)
   - [A4. OFAC SDN List — Unprecedented Expansion](#a4-ofac-sdn-list--unprecedented-expansion)
   - [A5. Maduro Regime Financial Flows Through DR](#a5-maduro-regime-financial-flows-through-dr)
   - [A6. Crypto & Alternative Payment Risks](#a6-crypto--alternative-payment-risks)
   - [A7. Scotiabank DR — VZ-Specific Risk Vectors](#a7-scotiabank-dr--vz-specific-risk-vectors)
3. [PART B: Mexico (MEX)](#part-b-mexico-mex)
   - [B1. Cartel Decapitation — Unprecedented Dual Crisis](#b1-cartel-decapitation--unprecedented-dual-crisis)
   - [B2. Route Displacement to DR (Balloon Effect)](#b2-route-displacement-to-dr-balloon-effect)
   - [B3. Fentanyl Supply Chain & Dominican Distributors](#b3-fentanyl-supply-chain--dominican-distributors)
   - [B4. US-Mexico Drug Policy Under Trump](#b4-us-mexico-drug-policy-under-trump)
   - [B5. TBML — Tariffs, Gold, and Free Trade Zones](#b5-tbml--tariffs-gold-and-free-trade-zones)
   - [B6. Scotiabank Mexico-DR Cross-Border Exposure](#b6-scotiabank-mexico-dr-cross-border-exposure)
   - [B7. Recent OFAC/FinCEN Actions](#b7-recent-ofacfincen-actions)
4. [Combined Risk Matrix](#4-combined-risk-matrix)
5. [Model Development Implications](#5-model-development-implications)
6. [Sources](#6-sources)

---

## 1. Executive Summary

**Bottom line:** Venezuela and Mexico risks for Scotiabank DR are at their highest point in the bank's history in the Dominican Republic. Two simultaneous geopolitical shocks demand immediate model recalibration:

**Venezuela:**
- Maduro captured by US forces (Jan 3, 2026); $700M in assets seized including a mansion in **Cap Cana, DR**
- 80% of PDVSA oil revenue now flows through USDT stablecoins (Tether/Tron)
- SDN list expanding at unprecedented pace — dozens of new designations in Dec 2025 alone
- Banco Peravia precedent: Venezuelan billionaire acquired a DR bank to launder $1B+
- TPS termination for ~300K Venezuelans pushes migration to irregular channels
- ~3 go-fast boats/week from Venezuela carrying 700kg-1 ton cocaine each to DR waters

**Mexico:**
- Both major cartels decapitated simultaneously (Zambada guilty plea Aug 2025; El Mencho killed Feb 22, 2026)
- Balloon effect actively displacing routes to Caribbean/DR — cocaine seizures up **fivefold** since 2019
- 8 cartels designated as Foreign Terrorist Organizations — material support is now a federal crime
- FinCEN designated 3 Mexican banks as primary money laundering concerns (first-ever use of FEND Off Fentanyl Act)
- Dominican nationals running fentanyl distribution networks in US Northeast (6+ major DEA prosecutions 2024-2025)
- DR gold/jewelry exports surging (+42%) through Free Trade Zones — flagged by OECD for illicit gold flows
- Scotiabank operates in **both** Mexico and DR, creating unique cross-border AML exposure

---

# PART A: VENEZUELA (VZ)

---

## A1. US Sanctions Landscape — Extreme Flux

### Sanctions Tightening (Early-Mid 2025)

| Date | Action | Detail |
|------|--------|--------|
| Feb 20, 2025 | FTO designation | **Tren de Aragua** designated as Foreign Terrorist Organization |
| Feb 26, 2025 | Chevron license revoked | OFAC GL 41A — Chevron must wind down Venezuela JV by April 3, 2025 (extended to May 27 via GL 41B) |
| April 2025 | Oil import tariffs | Any country importing Venezuelan oil faces **25% tariffs** on US exports |
| Jul 25, 2025 | SDGT designation | **Cartel de los Soles** designated as Specially Designated Global Terrorist, described as "headed by Maduro" |
| Dec 19, 2025 | SDN expansion | 7 individuals linked to Maduro's inner circle and PdVSA corruption |
| Dec 31, 2025 | Shadow fleet | 4 companies and 4 tankers designated for oil sanctions evasion |

**Refs:** [Miller & Chevalier](https://www.millerchevalier.com/publication/trade-compliance-flash-ofac-rescinds-venezuela-license-providing-oil-sanctions-relief), [Treasury - Cartel de los Soles](https://home.treasury.gov/news/press-releases/sb0207), [OFAC Dec 19](https://ofac.treasury.gov/recent-actions/20251219), [Treasury - Shadow Fleet](https://home.treasury.gov/news/press-releases/sb0348)

### The Maduro Capture (Jan 3, 2026)

US forces captured Maduro and wife Cilia Flores in Caracas; transported to SDNY. Superseding indictment charged **narco-terrorism conspiracy, cocaine importation conspiracy, and weapons offenses**. Co-defendants include Diosdado Cabello, Nicolas Maduro Guerra, and Tren de Aragua leader Nino Guerrero.

**Refs:** [PBS](https://www.pbs.org/newshour/world/a-timeline-of-u-s-military-escalation-against-venezuela-leading-to-maduros-capture), [NPR](https://www.npr.org/2026/01/03/nx-s1-5665617/venezuela-nicolas-maduro-charges)

### Post-Maduro Partial Sanctions Relief (Jan 2026)

- **Jan 9, 2026:** EO 14373 — "Safeguarding Venezuelan Oil Revenue for the Good of the American and Venezuelan People"
- **Jan 29, 2026:** OFAC GL 46 — permits Venezuela-origin oil transactions, but **only for established US entities** organized before Jan 29, 2025. Payments to blocked persons must go to Foreign Government Deposit Funds.

**Refs:** [Sullivan & Cromwell](https://www.sullcrom.com/insights/memo/2026/January/OFAC-Issues-Venezuelan-Oil-Related-General-License), [Holland & Knight](https://www.hklaw.com/en/insights/publications/2026/02/ofac-authorizes-certain-venezuelan-oil-sector-activities)

### AML Implication

The sanctions landscape is in **extreme flux**. GL 46 reopens some oil-sector transactions but with strict conditions. The SDN list is being updated at unprecedented pace. Any client with even indirect ties to PdVSA, GoV, Cartel de los Soles, or Tren de Aragua is a sanctions exposure. The post-Maduro political transition creates confusion about which Venezuelan entities are still blocked vs. now permissible. **Conservative interpretation is essential.**

---

## A2. Venezuela-DR Drug Trafficking Corridor

### Scale

- ~**3 go-fast boats/week** from Venezuela's Guajira and Paraguana peninsulas carrying 700kg-1 ton of cocaine each
- 3-4 out of every 5 boats include Venezuelan crew members
- Dominican traffickers meet at sea for load transfers; Venezuelan crews return south
- **DNCD seized 31.3 metric tons** of narcotics within DR territory in 2025, plus 17 metric tons in international ops

**Ref:** [InSight Crime](https://insightcrime.org/investigations/dominican-republic-venezuela-cocaine-across-caribbean/), [State Dept FY2026 Determination](https://www.state.gov/releases/office-of-the-spokesperson/2025/09/presidential-determination-on-major-drug-transit-or-major-illicit-drug-producing-countries-for-fiscal-year-2026)

### Operation Southern Spear (Sep 2025 — Present)

The US launched its **largest military presence in the Caribbean since the Cuban Missile Crisis:**
- USS Gerald R. Ford carrier strike group deployed Nov 2025
- As of Feb 23, 2026: **151+ people killed** in 44 strikes on 45 vessels
- **Sep 19, 2025:** First joint US-DR operation destroyed a drug boat; 1,000 kg cocaine recovered
- FY2025 Coast Guard intercepted **231,000 kg cocaine** — highest on record, triple the yearly average
- Defense Secretary Hegseth visited DR (Nov 2025) to bolster joint mission

**Refs:** [Wikipedia - Op Southern Spear](https://en.wikipedia.org/wiki/United_States_strikes_on_alleged_drug_traffickers_during_Operation_Southern_Spear), [CSIS](https://www.csis.org/analysis/trumps-caribbean-campaign-data-behind-developing-conflict), [CBS News](https://www.cbsnews.com/news/coast-guard-dea-defend-strikes-on-alleged-drug-boats-venezuela/)

### AML Implication

Military operations disrupt but do not eliminate trafficking — they push laundering into alternative channels. The volume (31+ metric tons seized in DR alone) implies **far more getting through**. Scotiabank DR faces enormous laundering pressure through cash-intensive businesses (nightclubs, real estate, casinos) and transaction monitoring must account for structuring patterns tied to narco-proceeds.

---

## A3. Venezuelan Migration & Remittance Risk

### Migration Scale

- DR repatriated **276,215 foreigners in irregular status** in January 2025 alone
- TPS termination for ~300,000 Venezuelans in US (Nov 2025) — some may redirect toward Caribbean/DR
- Supreme Court cleared TPS termination in Oct 2025, overturning five lower court rulings

**Refs:** [Migration Policy Institute](https://www.migrationpolicy.org/article/latin-america-caribbean-new-migration-era), [SCOTUSblog](https://www.scotusblog.com/2025/10/supreme-court-allows-trump-to-remove-protected-status-from-venezuelan-nationals/)

### Remittance Corridor

- DR received **$10.756 billion** in remittances in 2024 (+5.9% YoY)
- Q1 2025: $2.64B (+6.2% YoY)
- **80%+ flows from US**; average $300+ per send, 16 sends/year
- AOCRD-ADOCAMBIO implementing new AML controls in foreign exchange sector

**Refs:** [Dominican Today](https://dominicantoday.com/dr/economy/2025/01/10/dominican-republic-receives-us10756-million-in-remittances-in-2024/), [Inter-American Dialogue](https://thedialogue.org/blogs/2025/08/the-marketplace-for-money-transfers-to-the-dominican-republic-an-assessment/), [FinCrime Central](https://fincrimecentral.com/aml-foreign-exchange-dominican-republic-2025/)

### AML Implication

The $10.8B remittance corridor is an enormous attack surface. Venezuelan migrants with irregular status may use informal channels. Structuring through multiple remittance agents is a key typology. Scotiabank DR needs robust transaction monitoring tuned to remittance patterns, particularly for Venezuelan-origin clients.

---

## A4. OFAC SDN List — Unprecedented Expansion

| Date | Action | Targets |
|------|--------|---------|
| Feb 20, 2025 | FTO designation | Tren de Aragua |
| Jun 2025 | SDGT | Giovanni Mosquera Serrano (TdA fugitive leader) |
| Jul 17, 2025 | SDGT | Nino Guerrero + 5 TdA leaders |
| Jul 25, 2025 | SDGT | Cartel de los Soles (headed by Maduro) |
| Dec 3, 2025 | Counter-terrorism | TdA money laundering network (5 individuals) |
| Dec 11, 2025 | Counter-narcotics | 3 Maduro nephews, 6 shipping companies, 6 vessels |
| Dec 19, 2025 | EO 13850 | 7 individuals tied to PdVSA/Maduro inner circle |
| Dec 31, 2025 | Oil evasion | 4 companies, 4 tankers (shadow fleet) |

**Refs:** [OFAC Recent Actions](https://ofac.treasury.gov/recent-actions), [Treasury - TdA ML Network](https://home.treasury.gov/news/press-releases/sb0327)

### AML Implication

Screening list updates must be **near real-time**. The December 2025 wave added shipping companies, vessels, and individuals who may have correspondent banking relationships in the Caribbean. Scotiabank DR must screen against Maduro family members, PdVSA-linked businesspeople, TdA affiliates, and Cartel de los Soles entities.

---

## A5. Maduro Regime Financial Flows Through DR

### $700M Asset Seizure (Aug 2025)

DOJ seized ~$700M in Maduro-linked assets including:
- **Villa La Caracola** in Cap Cana, DR — 3,000 sqm oceanfront mansion, 9 bedrooms, in luxury Punta Cana resort area
- Florida homes, private jets, yachts, 9 luxury cars, horse farm, jewelry, cash
- Seizures conducted **in cooperation with DR authorities**

**Refs:** [MercoPress](https://en.mercopress.com/2025/08/14/us-seizes-assets-from-maduro-worth-us-700-million-bondi-says), [Latin Times](https://www.latintimes.com/inside-villa-la-caracola-18m-dominican-mansion-linked-maduro-reportedly-seized-us-588416)

### Banco Peravia Precedent

Venezuelan billionaire Raul Gorrin (Globovision owner) **acquired Banco Peravia in the DR specifically to launder $1B+ in bribes** from the Venezuelan treasury. The former Venezuelan national treasurer pled guilty; forfeiture judgment of $1B.

**Refs:** [DOJ](https://www.justice.gov/archives/opa/pr/venezuelan-billionaire-news-network-owner-former-venezuelan-national-treasurer-and-former), [ICE](https://www.ice.gov/news/releases/venezuelan-billionaire-charged-former-venezuelan-national-treasurer-and-former-owner)

### AML Implication

The Banco Peravia case is a **direct precedent** for how Venezuelan kleptocrats use DR banks as laundering vehicles. The Cap Cana property seizure confirms DR remains a destination for regime-linked wealth. Enhanced due diligence on any high-net-worth clients with Venezuelan connections — particularly in luxury real estate — is critical. PEP screening must cover Venezuelan political figures comprehensively.

---

## A6. Crypto & Alternative Payment Risks

### PDVSA Oil-for-USDT

- **80% of PDVSA oil revenue** now flows through USDT (Tether) stablecoins on the Tron network
- Started in 2023-2024 when PDVSA began requiring new clients to use digital wallets
- Off-exchange USDT transactions exceeded **$70 billion in 2025** (up from $26B in early 2023)
- Venezuela had **$44.6B in crypto transaction volume** in 2025 — top 5 in Latin America

**Refs:** [Atlantic Council](https://www.atlanticcouncil.org/blogs/new-atlanticist/how-venezuela-uses-crypto-to-sell-oil-and-what-the-us-should-do-about-it/), [Chainalysis](https://www.chainalysis.com/blog/latin-america-crypto-adoption-2025/)

### Tether Enforcement

- **Jan 11, 2026:** Tether froze **$182M in USDT** across 5 Tron wallets — largest single-day action ever — in wake of Maduro capture
- By 2024, Tether had already frozen 41 wallets for Venezuela sanctions evasion
- Illicit crypto flows reached **$158B in 2025** (145% increase from 2024); stablecoins = **84% of illicit volume**

**Refs:** [Yahoo Finance](https://finance.yahoo.com/news/tether-freezes-182m-usdt-largest-105442400.html), [BlockEden](https://blockeden.xyz/blog/2026/01/25/tether-182-million-usdt-freeze-venezuela-stablecoin-enforcement/)

### Dual-Use Reality

- ~9% of Venezuela's $5.4B in remittances flows through crypto
- 38%+ of Venezuelan crypto activity is peer-to-peer
- Projected 682% inflation in 2026 — USDT is a survival tool, not just evasion

**Ref:** [Crowdfund Insider](https://www.crowdfundinsider.com/2025/12/256449-venezuelas-crypto-ecosystem-continues-to-evolve-amid-global-tension-analysis/)

### AML Implication

Even if Scotiabank DR does not directly handle crypto, the **off-ramp risk is critical**. Venezuelan clients converting USDT to fiat through exchanges then depositing into bank accounts creates tainted fund flows. The P2P nature (38%) means informal conversion channels bypassing KYC. Scotiabank needs VASP-aware transaction monitoring and red flags for crypto-to-fiat patterns.

---

## A7. Scotiabank DR — VZ-Specific Risk Vectors

**Scotiabank DR position:** 3rd-largest private bank, $328M acquisition of Banco Dominicano del Progreso (2019), RD$140B+ in assets, 10% market share, 57+ branches, 250K+ customers.

**Scotiabank stated policy:** "Scotiabank does not undertake any transaction related to the provision of financing for or any other dealing involving the Venezuelan Government." Zero appetite for ML/TF/sanctions violations.

**Scotiabank LatAm strategy:** Exited Panama, Costa Rica, Colombia — **but kept DR and Caribbean**, where profitability was highest in a decade.

### Top 10 VZ-Related Risk Vectors

1. **SDN Screening Velocity** — Dozens of new designations in Dec 2025 alone. Near real-time updates required.
2. **PEP Exposure** — Maduro capture, $700M seizure (including Cap Cana), Banco Peravia precedent. Venezuelan PEP screening must extend to family, associates, front companies.
3. **Narco-Proceeds Washing** — 31+ metric tons seized in DR in 2025. Cash-intensive businesses are primary vehicles.
4. **Remittance Corridor Risk** — $10.8B US-DR corridor. Monitor unusual patterns from Venezuelan nationals.
5. **Crypto Off-Ramp** — 80% of PDVSA revenue in USDT. Watch for crypto-to-fiat deposit patterns.
6. **Post-Maduro Transition** — GL 46 reopens some oil transactions with strict conditions. Conservative interpretation essential.
7. **Correspondent Banking** — Re-evaluate any relationships touching Venezuelan oil flows, PdVSA subsidiaries, shadow fleet companies.
8. **TdA Money Laundering Networks** — Treasury specifically targeted TdA financial infrastructure (Dec 2025). Entertainment industry fronts and informal networks.
9. **Regulatory Scrutiny** — DR's FATF deficiencies + heightened US focus on VZ-DR corridor. OSFI (Canada) and DR Superintendency both watching.
10. **Real Estate Laundering** — Cap Cana/Punta Cana luxury real estate is a confirmed destination for Venezuelan dirty money.

---

# PART B: MEXICO (MEX)

---

## B1. Cartel Decapitation — Unprecedented Dual Crisis

### Sinaloa Cartel: Post-Zambada Collapse

**Ismael "El Mayo" Zambada** captured July 2024 in El Paso; pled guilty August 25, 2025 to racketeering conspiracy and running a continuing criminal enterprise. Faces mandatory life.

**Aftermath:** Homicides in Sinaloa state rose **400%** in the year following capture. Nearly 2,000 killed in factional warfare between "Los Mayitos" (Zambada loyalists) and "Los Chapitos" (Guzman family).

**Refs:** [DOJ](https://www.justice.gov/opa/pr/co-founder-sinaloa-cartel-ismael-el-mayo-zambada-garcia-pleads-guilty-engaging-continuing), [CNN](https://www.cnn.com/2025/08/18/americas/mexico-killings-sinaloa-cartel-kingpin-latam-intl)

### CJNG: El Mencho Killed (February 22, 2026 — 4 days ago)

Mexican military, aided by US intelligence, **killed Nemesio "El Mencho" Oseguera Cervantes** in Tapalpa, Jalisco. The most significant cartel decapitation in years.

**Immediate aftermath:**
- 25+ National Guard members killed in retaliation
- 250+ roadblocks across 20 Mexican states
- Vehicle fires, attacks on stores, widespread chaos
- Succession line "broken" — son "El Menchito" in US custody, no clear family successor

**Refs:** [CNN](https://www.cnn.com/2026/02/22/americas/mexico-kill-drug-mencho-latam-intl), [NBC News](https://www.nbcnews.com/world/mexico/jalisco-new-generation-cartel-leader-killed-rcna260184), [Vision of Humanity](https://www.visionofhumanity.org/el-mencho-is-dead-mexicos-fragile-peace-now-faces-its-biggest-test-in-years/)

### AML Implication

**Both major Mexican cartels are in leadership crises simultaneously — unprecedented.** When organizations fragment, they do not disappear — they **metastasize**. Expect new, less predictable actors seeking new routes and financial channels. Smaller factions may be harder to track via traditional screening.

---

## B2. Route Displacement to DR (Balloon Effect)

### Historical Pattern

The balloon effect is thoroughly established:
- 1980s: Caribbean crackdown → routes shifted overland through Central America and Mexico
- Post-2009: Mexican crackdowns → **routes reversing back to Caribbean**
- Pacific coast maritime trafficking rose 73% as overland smuggling became harder

### Current Displacement (2025-2026) — Evidence

| Indicator | Data |
|-----------|------|
| DR cocaine seizures 2019 | ~6 tons |
| DR cocaine seizures 2024 | **30+ tons** (fivefold increase) |
| DR drug-related arrests 2025 | 46,367 |
| Firearms confiscated 2025 | 404 |
| Sinaloa Caribbean routes | Established through DR; buying cocaine in Venezuela, contracting Venezuelans for maritime transport |
| Port of Caucedo | 2.2 tons intercepted en route to Antwerp, Belgium — DR as transit for European markets |
| European premium | $28K/kg US vs. $40K-$80K/kg Europe — increasing attractiveness of DR-Europe route |

**Refs:** [InSight Crime](https://insightcrime.org/news/dominican-republic-breaks-seizure-record-amid-renewed-caribbean-trafficking/), [Dominican Today](https://dominicantoday.com/dr/local/2026/01/02/dominican-government-highlights-anti-drug-efforts-in-2025/), [CSIS](https://features.csis.org/tracking-transatlantic-drug-flows-cocaines-path-from-south-america-across-the-caribbean-to-europe/)

### AML Implication

The balloon effect doesn't just move drugs — **it moves money**. When trafficking routes shift to the Caribbean, associated financial flows (proceeds laundering, payment for services, logistics financing) shift to Caribbean banking systems. The dual cartel disruption in Mexico (Zambada + El Mencho) creates **maximum displacement pressure** on DR financial institutions.

---

## B3. Fentanyl Supply Chain & Dominican Distributors

### Dominican-Led US Northeast Networks (2025 Prosecutions)

| Date | Case | Detail |
|------|------|--------|
| Feb 2025 | Jiminez Pujols | Multiple distribution points across NE US; pled guilty to 40+ grams fentanyl |
| May 2025 | 65K pills | Dominican national arrested for conspiracy to distribute ~65,000 fentanyl pills |
| Sep 2025 | Bronx fentanyl mill | 6 Dominican nationals arrested processing 8+ kg fentanyl powder; face life |
| Sep 2025 | Jairo Collazo | Sentenced to 10 years for distributing fentanyl in Massachusetts from Bronx |
| Nov 2025 | Valdez De Los Santos | **Extradited from DR** for coordinating distribution via encrypted messaging |
| Dec 2025 | Plea deal | Dominican national pled guilty to trafficking tens of thousands of fentanyl pills |

**Refs:** [DOJ - Bronx mill](https://www.justice.gov/usao-sdny/pr/six-defendants-charged-operating-fentanyl-mill-manufactured-and-sold-millions-worth), [DEA - Collazo](https://www.dea.gov/press-releases/2025/09/24/dominican-national-sentenced-decade-prison-for-fentanyl-distribution), [DOJ - Extradition](https://www.justice.gov/usao-nh/pr/dominican-authorities-extradite-united-states-international-drug-supplier-who)

### Precursor Chemical Disruption

- China completed scheduling all fentanyl precursors per INCB requirements (June 2025)
- Mexico-based producers having **difficulty obtaining key precursors**
- US fentanyl overdose deaths declining
- **But:** FinCEN identified **$312 billion in suspicious transactions** associated with Chinese Money Laundering Networks (CMLNs) connecting Chinese suppliers → Mexican cartels → US proceeds

**Refs:** [CRS](https://www.congress.gov/crs_external_products/IF/HTML/IF10400.html), [FinCEN - CMLN Advisory](https://www.fincen.gov/news/news-releases/fincen-issues-advisory-and-financial-trend-analysis-chinese-money-laundering)

### AML Implication

Dominican nationals are the **last-mile distributors** for fentanyl in the US Northeast. Proceeds flow back to DR via remittances, structured deposits, and crypto. The extradition from DR (Nov 2025) confirms in-country coordination. Scotiabank DR must build transaction monitoring rules tuned to fentanyl-distribution proceeds patterns: rapid small deposits, encrypted app usage, and US Northeast geographic nexus.

---

## B4. US-Mexico Drug Policy Under Trump

### Cartel Terrorist Designations

**8 cartels** designated as Foreign Terrorist Organizations (FTOs) and Specially Designated Global Terrorists (SDGTs):
- Sinaloa, CJNG, Gulf Cartel, Cartel of the Northeast, and others
- Trump signed directive allowing **US military action** against designated cartels

**Ref:** [White House EO, Jan 2025](https://www.whitehouse.gov/presidential-actions/2025/01/designating-cartels-and-other-organizations-as-foreign-terrorist-organizations-and-specially-designated-global-terrorists/)

### Tariffs as Leverage

- **25% tariffs** on Mexican imports from March 2025 under IEEPA
- July 2025: 90-day pause on increase to 30%

### Mexico's Response

- 10,000 additional National Guard troops deployed to border
- Fentanyl seizures nearly matched full prior year in 5 months
- 29 high-value targets transferred to US custody
- **El Mencho killed** (Feb 22, 2026) with US intelligence assistance

### Operation Southern Spear

- Largest US military Caribbean presence since Cuban Missile Crisis
- 151+ killed in 44 strikes on 45 vessels
- Joint US-DR operations including 484 kg cocaine seizure (Nov 2025)
- DR President authorized US operations in restricted Caribbean areas

**Refs:** [WOLA](https://www.wola.org/analysis/trump-tariffs-fentanyl-migration-u-s-mexico/), [Wikipedia - Op Southern Spear](https://en.wikipedia.org/wiki/United_States_strikes_on_alleged_drug_traffickers_during_Operation_Southern_Spear)

### AML Implication

The FTO designation means **any financial transaction knowingly providing material support to designated cartels is a federal crime** with severe penalties. This dramatically raises compliance stakes for any bank operating in territories where these cartels move money. DR is squarely in that territory.

---

## B5. TBML — Tariffs, Gold, and Free Trade Zones

### Free Trade Zones as TBML Vectors

FATF and OECD have both flagged DR's Free Trade Zones as high-risk:
- Reduced customs controls
- Invoice manipulation (over/under-invoicing)
- Relaxed oversight exploited for laundering

### Gold & Jewelry — Major Red Flag

**Jewelry and gold are now DR's leading export category (2025):**

| Metric | Value |
|--------|-------|
| Total DR exports 2025 | Record **$14.65 billion** (+13.41%) |
| Precious stones/pearls share | **45.08%** of national regime exports |
| Gold export growth | +15% |
| Jewelry category growth | **+42%** to $397.1 million |
| National regime export growth | +36.77% to $5.46 billion |

The OECD specifically notes DR is "both a gold producer and a transit hub for gold in a variety of forms, much of which passes through its FTZs."

**Refs:** [DR1.com](https://dr1.com/news/2026/01/22/jewelry-and-gold-lead-dominican-export-surge-in-2025/), [OECD](https://www.oecd.org/en/publications/free-trade-zones-and-illicit-gold-flows-in-latin-america-and-the-caribbean_7536db96-en.html), [FATF - FTZ](https://www.fatf-gafi.org/en/publications/Methodsandtrends/Moneylaunderingvulnerabilitiesoffreetradezones.html)

### Tariffs Amplifying TBML Risk

The 25% US tariffs on Mexico are directly **fueling TBML**: rising tariffs give criminals greater motivation to exploit trade channels through invoice manipulation and transshipment routes.

**Refs:** [Stratfor](https://worldview.stratfor.com/article/tariffs-sanctions-and-problem-trade-based-money-laundering-drug-cartels-terrorism-financial-regulations), [Forvis Mazars](https://www.forvismazars.us/forsights/2025/09/tariffs-financial-crime-risks-for-financial-institutions)

### AML Implication

The gold/jewelry export surge (+42%) is a **critical TBML red flag**. DR FTZs are confirmed conduits for illicit gold. US tariffs on Mexico incentivize re-routing trade through DR. Scotiabank DR must implement trade finance monitoring rules for gold/jewelry exporters and flag anomalous FTZ-related transactions.

---

## B6. Scotiabank Mexico-DR Cross-Border Exposure

### Strategic Position

Scotiabank operates in **both Mexico and DR**, creating unique cross-border AML exposure:

| Market | Position |
|--------|----------|
| DR | 3rd-largest private bank, ~10% market share, 70+ branches |
| Mexico | Core "North American Rebirth" strategy market; USMCA trade corridor facilitator |
| US | 14.9% stake in KeyCorp — creating Canada-US-Mexico-DR banking corridor |
| LatAm exits | Sold Colombia, Costa Rica, Panama (Dec 2025) — **concentrating in Mexico and DR** |

### Cross-Border Risk Vectors

1. **Correspondent banking:** Scotiabank Mexico may process transactions touching DR operations. FinCEN's designation of 3 Mexican banks shows any institution can be targeted.
2. **USMCA trade finance:** The bank's positioning as a trade corridor facilitator means TBML risk is **inherent in its value proposition**.
3. **Concentrated exposure:** By exiting Central America but keeping Mexico and DR, Scotiabank has concentrated in two high-risk narco-transit jurisdictions.

**Refs:** [PR Newswire - BDP acquisition](https://www.prnewswire.com/news-releases/scotiabank-completes-acquisition-of-97-44-of-banco-dominicano-del-progreso-853784597.html), [Banking Dive - KeyCorp](https://www.bankingdive.com/news/scotiabank-keybank-fed-approval-14-stake/735488/)

---

## B7. Recent OFAC/FinCEN Actions

### FinCEN Actions (2025)

| Date | Action | DR Relevance |
|------|--------|--------------|
| Mar 31, 2025 | Bulk Cash Smuggling Alert | Mexico TCOs using front businesses to repatriate cash. Watch for similar DR patterns. |
| Jun 25, 2025 | **Section 311: CIBanco, Intercam, Vector** | **First-ever FEND Off Fentanyl Act use.** CIBanco processed $2.1M for China-based precursor suppliers. US banks barred from transacting. |
| Aug 2025 | CMLN Advisory | $312B in suspicious CMLN-related transactions (2020-2024). CMLNs facilitate cartel proceeds laundering. |
| Nov 2025 | Cross-Border Bulk Cash Alert | Updated red flags for cash repatriation schemes. |

### OFAC Actions (2025)

| Date | Action | DR Relevance |
|------|--------|--------------|
| Jan 2025 | 8 cartels as FTO/SDGT | Material support = federal crime. Banks in drug-transit countries face elevated scrutiny. |
| Oct 30, 2025 | TCO designations | Additional cartel-linked individuals/entities on SDN list. |
| Nov 2025 | Hysa OCG + Mexico gambling | 27 individuals/entities sanctioned; 10 Mexico gambling establishments targeted. |

### DR-Specific Designations

- **Jose Calderon Rijo ("La Arana")** — E.O. 14059; leader of most significant DR criminal organization
- **Peralta DTO** — Kingpin Act; 8 Dominican nationals, 6 Santo Domingo entities

### DR Domestic AML Developments (2025)

- Landmark AML agreement: AOCRD-ADOCAMBIO for foreign exchange sector
- Resolution 217-2025: Mandated certified compliance officer training
- President Abinader: Bill to regulate gambling sector for AML (June 2025)
- Drug trafficker extradited from DR to Puerto Rico (Jan 2026) — laundered $400K via crypto
- European prosecutors seized DR bank accounts (Jul 2025) — €25M VAT fraud

**Refs:** [FinCEN - CIBanco](https://home.treasury.gov/news/press-releases/sb0179), [FinCEN - CMLN](https://www.fincen.gov/news/news-releases/fincen-issues-advisory-and-financial-trend-analysis-chinese-money-laundering), [g3newswire](https://g3newswire.com/dominican-republic-signs-landmark-agreement-to-strengthen-anti-money-laundering-measures/)

---

## 4. Combined Risk Matrix

| Risk Factor | Source | Severity | Trend | Priority |
|-------------|--------|----------|-------|----------|
| Dual cartel decapitation → route displacement to DR | MEX | Critical | ↑ Worsening | Immediate |
| Maduro capture → sanctions flux & VZ capital flight | VZ | Critical | ↑ Worsening | Immediate |
| SDN list expansion velocity | VZ | High | ↑ Accelerating | Immediate |
| Fentanyl distribution by DR nationals | MEX | High | → Stable-High | High |
| PDVSA 80% USDT → crypto off-ramp risk | VZ | High | ↑ Growing | High |
| FTZ gold/jewelry exports (+42%) → TBML | MEX/VZ | High | ↑ Growing | High |
| TPS termination → irregular VZ migration | VZ | High | ↑ New | High |
| FTO cartel designations → material support liability | MEX | High | New | High |
| Operation Southern Spear → route adaptation | VZ/MEX | Medium-High | → Evolving | Medium |
| Chinese MLN → precursor financing | MEX | Medium-High | → Stable | Medium |
| Scotiabank Mexico-DR corridor concentration | MEX | Medium-High | ↑ Increasing | Medium |
| Banco Peravia-type acquisition risk | VZ | Medium | → Latent | Medium |
| $10.8B remittance corridor exploitation | VZ/MEX | High | → Stable-High | High |
| Real estate laundering (Cap Cana/Punta Cana) | VZ | Medium-High | → Stable | Medium |
| Correspondent banking re-evaluation | VZ/MEX | Medium | ↑ New scrutiny | Medium |

---

## 5. Model Development Implications

### For the AML Chief Model Developer

#### Rule-Based Model Updates Needed

| Rule Category | Trigger | Rationale |
|---------------|---------|-----------|
| **OFAC screening frequency** | Increase to near real-time | SDN list updating at unprecedented pace; Dec 2025 alone added dozens of entries |
| **VZ PEP cascade** | Extend to 3rd-degree connections | Maduro capture revealed deep network; Banco Peravia showed front company layers |
| **Crypto off-ramp detection** | New rule set | Flag deposits following crypto exchange withdrawal patterns; USDT-to-fiat sequences |
| **Fentanyl proceeds patterns** | New rule set | Small rapid deposits, US NE geographic nexus, encrypted app correlates |
| **FTZ gold/jewelry thresholds** | Lower monitoring thresholds | +42% growth rate is anomalous; OECD-flagged sector |
| **Cartel FTO material support** | New screening layer | 8 designated organizations; any linked transaction is federal crime |
| **TPS-terminated migrant patterns** | Enhanced monitoring | Newly irregular status → informal channel usage |
| **Bulk cash structuring** | Recalibrate thresholds | Increased narco-proceeds pressure from route displacement |

#### Anomaly Detection Feature Engineering

| Feature | Type | Rationale |
|---------|------|-----------|
| `vz_nationality_flag` | Binary | Venezuelan clients flagged for enhanced monitoring given sanctions flux |
| `crypto_exchange_deposit_ratio` | Ratio | Proportion of deposits originating from known crypto exchange accounts |
| `ftz_gold_export_velocity` | Time-series | Rapid increase in FTZ-routed gold/jewelry export financing |
| `us_northeast_remittance_cluster` | Geographic | Concentration of inbound remittances from NE US (fentanyl proceeds corridor) |
| `pep_proximity_score` | Score | Degree of connection to Venezuelan or Mexican PEPs (network analysis) |
| `post_designation_transaction_spike` | Time-series | Transaction volume changes following new OFAC designations |
| `cartel_fto_name_fuzzy_match` | Score | Fuzzy matching against FTO-designated cartel entity names and aliases |
| `tariff_arbitrage_invoice_ratio` | Ratio | Invoice values vs. market prices for Mexico/DR trade (TBML signal) |
| `irregular_migration_deposit_pattern` | Behavioral | Small deposits from newly opened accounts by foreign nationals with limited history |
| `operation_southern_spear_geographic` | Geographic | Transaction activity from coastal areas where interceptions are occurring |

---

## 6. Sources

### Venezuela Sources

| # | Source | URL |
|---|--------|-----|
| V1 | Miller & Chevalier — Chevron GL 41A | https://www.millerchevalier.com/publication/trade-compliance-flash-ofac-rescinds-venezuela-license-providing-oil-sanctions-relief |
| V2 | Treasury — Cartel de los Soles designation | https://home.treasury.gov/news/press-releases/sb0207 |
| V3 | Treasury — TdA ML Network | https://home.treasury.gov/news/press-releases/sb0327 |
| V4 | Treasury — Shadow Fleet | https://home.treasury.gov/news/press-releases/sb0348 |
| V5 | OFAC — Dec 19 actions | https://ofac.treasury.gov/recent-actions/20251219 |
| V6 | PBS — Maduro capture timeline | https://www.pbs.org/newshour/world/a-timeline-of-u-s-military-escalation-against-venezuela-leading-to-maduros-capture |
| V7 | NPR — Maduro charges | https://www.npr.org/2026/01/03/nx-s1-5665617/venezuela-nicolas-maduro-charges |
| V8 | Sullivan & Cromwell — GL 46 | https://www.sullcrom.com/insights/memo/2026/January/OFAC-Issues-Venezuelan-Oil-Related-General-License |
| V9 | Holland & Knight — GL 46 | https://www.hklaw.com/en/insights/publications/2026/02/ofac-authorizes-certain-venezuelan-oil-sector-activities |
| V10 | InSight Crime — VZ-DR cocaine corridor | https://insightcrime.org/investigations/dominican-republic-venezuela-cocaine-across-caribbean/ |
| V11 | State Dept — FY2026 drug transit determination | https://www.state.gov/releases/office-of-the-spokesperson/2025/09/presidential-determination-on-major-drug-transit-or-major-illicit-drug-producing-countries-for-fiscal-year-2026 |
| V12 | Wikipedia — Operation Southern Spear | https://en.wikipedia.org/wiki/United_States_strikes_on_alleged_drug_traffickers_during_Operation_Southern_Spear |
| V13 | CSIS — Trump's Caribbean campaign | https://www.csis.org/analysis/trumps-caribbean-campaign-data-behind-developing-conflict |
| V14 | CBS News — Coast Guard seizures | https://www.cbsnews.com/news/coast-guard-dea-defend-strikes-on-alleged-drug-boats-venezuela/ |
| V15 | Migration Policy Institute — VZ migration | https://www.migrationpolicy.org/article/latin-america-caribbean-new-migration-era |
| V16 | SCOTUSblog — TPS termination | https://www.scotusblog.com/2025/10/supreme-court-allows-trump-to-remove-protected-status-from-venezuelan-nationals/ |
| V17 | Dominican Today — $10.8B remittances | https://dominicantoday.com/dr/economy/2025/01/10/dominican-republic-receives-us10756-million-in-remittances-in-2024/ |
| V18 | Inter-American Dialogue — remittance analysis | https://thedialogue.org/blogs/2025/08/the-marketplace-for-money-transfers-to-the-dominican-republic-an-assessment/ |
| V19 | FinCrime Central — DR foreign exchange AML | https://fincrimecentral.com/aml-foreign-exchange-dominican-republic-2025/ |
| V20 | MercoPress — $700M Maduro assets seized | https://en.mercopress.com/2025/08/14/us-seizes-assets-from-maduro-worth-us-700-million-bondi-says |
| V21 | Latin Times — Villa La Caracola | https://www.latintimes.com/inside-villa-la-caracola-18m-dominican-mansion-linked-maduro-reportedly-seized-us-588416 |
| V22 | DOJ — Banco Peravia / Gorrin | https://www.justice.gov/archives/opa/pr/venezuelan-billionaire-news-network-owner-former-venezuelan-national-treasurer-and-former |
| V23 | Atlantic Council — PDVSA crypto | https://www.atlanticcouncil.org/blogs/new-atlanticist/how-venezuela-uses-crypto-to-sell-oil-and-what-the-us-should-do-about-it/ |
| V24 | Chainalysis — LatAm crypto adoption | https://www.chainalysis.com/blog/latin-america-crypto-adoption-2025/ |
| V25 | Yahoo Finance — Tether $182M freeze | https://finance.yahoo.com/news/tether-freezes-182m-usdt-largest-105442400.html |
| V26 | Crowdfund Insider — VZ crypto ecosystem | https://www.crowdfundinsider.com/2025/12/256449-venezuelas-crypto-ecosystem-continues-to-evolve-amid-global-tension-analysis/ |
| V27 | Scotiabank — Sanctions Policy Statement | https://www.scotiabank.com/content/dam/scotiabank/canada/en/documents/ScotiabankGroupSanctionsPolicyStatement.pdf |

### Mexico Sources

| # | Source | URL |
|---|--------|-----|
| M1 | DOJ — Zambada guilty plea | https://www.justice.gov/opa/pr/co-founder-sinaloa-cartel-ismael-el-mayo-zambada-garcia-pleads-guilty-engaging-continuing |
| M2 | CNN — Sinaloa homicides 400% | https://www.cnn.com/2025/08/18/americas/mexico-killings-sinaloa-cartel-kingpin-latam-intl |
| M3 | CNN — El Mencho killed | https://www.cnn.com/2026/02/22/americas/mexico-kill-drug-mencho-latam-intl |
| M4 | NBC News — CJNG leader killed | https://www.nbcnews.com/world/mexico/jalisco-new-generation-cartel-leader-killed-rcna260184 |
| M5 | Vision of Humanity — El Mencho analysis | https://www.visionofhumanity.org/el-mencho-is-dead-mexicos-fragile-peace-now-faces-its-biggest-test-in-years/ |
| M6 | InSight Crime — DR seizure records | https://insightcrime.org/news/dominican-republic-breaks-seizure-record-amid-renewed-caribbean-trafficking/ |
| M7 | Dominican Today — 2025 drug arrests | https://dominicantoday.com/dr/local/2026/01/02/dominican-government-highlights-anti-drug-efforts-in-2025/ |
| M8 | CSIS — transatlantic cocaine flows | https://features.csis.org/tracking-transatlantic-drug-flows-cocaines-path-from-south-america-across-the-caribbean-to-europe/ |
| M9 | DOJ — Bronx fentanyl mill | https://www.justice.gov/usao-sdny/pr/six-defendants-charged-operating-fentanyl-mill-manufactured-and-sold-millions-worth |
| M10 | DEA — Collazo sentencing | https://www.dea.gov/press-releases/2025/09/24/dominican-national-sentenced-decade-prison-for-fentanyl-distribution |
| M11 | DOJ — Valdez extradition from DR | https://www.justice.gov/usao-nh/pr/dominican-authorities-extradite-united-states-international-drug-supplier-who |
| M12 | CRS — fentanyl precursors | https://www.congress.gov/crs_external_products/IF/HTML/IF10400.html |
| M13 | FinCEN — CMLN advisory | https://www.fincen.gov/news/news-releases/fincen-issues-advisory-and-financial-trend-analysis-chinese-money-laundering |
| M14 | White House — cartel FTO designation | https://www.whitehouse.gov/presidential-actions/2025/01/designating-cartels-and-other-organizations-as-foreign-terrorist-organizations-and-specially-designated-global-terrorists/ |
| M15 | WOLA — tariffs analysis | https://www.wola.org/analysis/trump-tariffs-fentanyl-migration-u-s-mexico/ |
| M16 | DR1.com — gold/jewelry exports | https://dr1.com/news/2026/01/22/jewelry-and-gold-lead-dominican-export-surge-in-2025/ |
| M17 | OECD — FTZ illicit gold | https://www.oecd.org/en/publications/free-trade-zones-and-illicit-gold-flows-in-latin-america-and-the-caribbean_7536db96-en.html |
| M18 | FATF — FTZ money laundering | https://www.fatf-gafi.org/en/publications/Methodsandtrends/Moneylaunderingvulnerabilitiesoffreetradezones.html |
| M19 | Stratfor — tariffs and TBML | https://worldview.stratfor.com/article/tariffs-sanctions-and-problem-trade-based-money-laundering-drug-cartels-terrorism-financial-regulations |
| M20 | Treasury — CIBanco Section 311 | https://home.treasury.gov/news/press-releases/sb0179 |
| M21 | Banking Dive — Scotiabank KeyCorp | https://www.bankingdive.com/news/scotiabank-keybank-fed-approval-14-stake/735488/ |
| M22 | PR Newswire — Scotiabank BDP acquisition | https://www.prnewswire.com/news-releases/scotiabank-completes-acquisition-of-97-44-of-banco-dominicano-del-progreso-853784597.html |
| M23 | g3newswire — DR AML agreement | https://g3newswire.com/dominican-republic-signs-landmark-agreement-to-strengthen-anti-money-laundering-measures/ |

---

*Research compiled February 26, 2026. All sources web-verified at time of research.*
