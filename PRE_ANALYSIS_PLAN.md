# Pre-Analysis Plan
**Title:** Talk or Substance? AI Disclosure in SEC Filings after ChatGPT
**Author:** Waqar Hussain
**Date:** 16 October 2026

## Status
Before this plan was committed, I ran descriptive AI-term counts on a pilot of 49 large U.S. firms, built the 10-K section-extraction pipeline, and tested a draft specificity rubric on 50 passages scored by an AI model (not yet by human coders). No hypothesis tests have been run and no outcome variables (ROA, returns) have been examined. Everything below is specified before analysis. Later changes will be recorded as dated amendments in AMENDMENTS.md, not edits to this file.

## Research question
Do firms' AI disclosures reflect real AI activity, and do future performance and returns distinguish specific disclosure from vague disclosure?

## Hypotheses
- H1: After Nov 30, 2022, AI mentions rise more than real AI activity does, so the washing gap widens, especially at firms with low pre-period AI exposure.
- H2: Substantive AI disclosure predicts higher next-year ROA. Vague AI disclosure does not.
- H3: Vague disclosers earn lower subsequent abnormal returns than substantive disclosers. Vague disclosure declines after the 2024 SEC AI-washing enforcement actions (supplementary test).

## Sample
U.S. firms filing 10-Ks on EDGAR, fiscal years 2019-2025. Exclude financials (SIC 6000-6999) and utilities (SIC 4900-4999). Only filings of form 10-K are used (amendments excluded); if two filings share a fiscal period, the longest is kept. A filing enters the Items 1/1A/7 sample only if each section is found, has at least 500 words, and appears in order without overlap; failing filings stay in the whole-filing sample. Report observation counts at each filter.

## Variables
- AI intensity: AI-term count per 1,000 words in Items 1, 1A, and 7 (term list in repo). The whole-filing count is a robustness check. A variant counts only AI text that is new relative to the firm's previous filing.
- Substantiveness: language-model score (0-3) per AI passage with a fixed rubric; firm-year share scoring 2 or 3. Validated against two human coders (Cohen's kappa reported).
- Vague intensity: AI intensity x (1 - substantiveness).
- Washing gap: residual of AI intensity regressed on AI patents, R&D/assets, capex/assets, log assets, and industry-year fixed effects.
- Outcomes: next-year ROA; abnormal returns (Fama-French factor model).
- Controls: log assets, leverage, R&D/assets, book-to-market, prior ROA.

## Main specifications
- H1: Gap_it = a_i + g_t + b(Post_t x Exposure_i) + controls + e. Exposure = 2019-2021 AI patent intensity. Firm and year fixed effects; errors clustered by firm.
- H2: ROA_i,t+1 = a_i + g_t + b1 Substantive_it + b2 Vague_it + controls + e. Same fixed effects and clustering.
- H3: (a) CAR[0,+2] around filing date on vague and substantive intensity. (b) Calendar-time portfolios, 12-month holding period. (c) DiD around 2024 enforcement (supplementary).

## Support criteria
H1 supported if b > 0 at 5%. H2 supported if b1 > 0 at 5% and b2 not significantly different from zero. H3 supported if vague-minus-substantive abnormal returns are negative at 5%.

## Robustness (planned)
Alternative term lists; second language model; excluding 2020; industry subsamples; placebo event dates; two-way clustering; whole-filing text instead of Items 1, 1A, 7.

## Exploratory analysis
Anything not listed above will be labeled exploratory in the paper.
