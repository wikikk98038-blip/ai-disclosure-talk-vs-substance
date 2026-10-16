# AI-Passage Specificity Codebook, version 1

**Date:** 2026-10-16
**Status:** Draft. Derived from a 7-passage calibration with one human rater (the author) and one model rater (Claude). Not yet validated. Test on fresh passages with two human coders before use in the paper.

## Unit
One passage = the sentence containing an AI term, plus the sentence before and after it, from Items 1, 1A, or 7 of a 10-K.

## Scores
| Score | Meaning |
|---|---|
| 0 | No firm action described. Risk, regulatory, or hypothetical wording; an AI term inside a list of service lines or a passing mention. |
| 1 | The firm says it uses, offers, or invests in AI, with no detail on what, where, or how. |
| 2 | The AI claim is tied to a named product, feature, or concrete use case. |
| 3 | As in 2, plus a specific number, date, or count linked to an AI action (an investment date, a count of units, spending, users, a result). |

## Rules
1. Judge the words only. Do not guess or look up the firm.
2. Score the most specific firm-action sentence in the passage.
3. If two scores fit, take the lower one.
4. A risk, regulatory, or hypothetical sentence is a 0, even when it names AI.
5. An AI term inside a list of service lines, or a regulatory statement, is a 0 (calibration passages 1 and 22).
6. A number that is not linked to an AI action (total revenue, number of integrations) does not make a 3.

## Headline measure
Substantive = score of 2 or 3. Vague = score of 1. Boilerplate = score of 0. The plan should report vague and boilerplate separately, since merging them mixes empty claims with risk language.

## Calibration passages (author = human rater, Claude = model rater)
| Passage | Author | Claude | Note |
|---|---|---|---|
| 1: AI listed within service lines | 0 | 1 | Rule 5 applies, author's reading adopted |
| 10: risk passage saying AI is integrated into platforms | 0 | 1 | OPEN: firm-action sentence inside a risk passage |
| 12: named tools plus "AI/ML" techniques | 2 | 1 | OPEN: named products not tied to AI |
| 15: "machine learning" in a capability list | 1 | 1 | Agreement |
| 20: dated investment in an AI company | 3 | 2 | Rule 3 broadened to dates and counts |
| 21: five innovation hubs including AI | 3 | 2 | Rule 3 broadened to dates and counts |
| 22: FDA wording with AI in new products | 0 | 1 | Rule 5 applies, author's reading adopted |

## Open questions
- Passage 10: does a firm-action sentence inside a risk passage score 1 or 0?
- Passage 12: does a list of named products count when only an "AI/ML" phrase refers to AI?
- Rule 3 now includes dates and counts, which will produce many 3s. Check on fresh passages whether the 2-versus-3 line stays usable.

## Next validation step
Draw 300 to 500 fresh passages at random, stratified by fiscal year and item. Have two human coders score them blind, report Cohen's kappa, and score the same passages with a named, versioned model for comparison. Do not reuse the calibration passages above as test items.
