## Data log
- Pilot: 50 random non-financial, non-utility S&P 500 firms (GICS filter, pilot only). Ticker Q had no 10-K in the window, so 49 firms.
- Only form "10-K" filings used (10-K/A excluded). Duplicates per fiscal period: longest kept.
- Sections (Items 1, 1A, 7) extracted with a rule-based splitter. Final pilot run: 369 filings, 353 pass all checks (95.7%), all 369 pass Items 1 and 1A. Failures: CLX (MD&A is in an exhibit) and PEP (Item 7 contains financial statements, excluded by name after manual inspection). Boundary audit of 12 random passing filings found no errors.
- Panel: 49 firms, fiscal years 2019-2025, no duplicate firm-years. Correlation between the section-based and whole-filing AI measures: 0.991.
- Pilot uses current S&P 500 membership (survivorship bias). The final sample will use all filers.
