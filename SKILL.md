---
name: childrens-rights-audit
description: Audit a digital product for children (game, app, site, concept, design, spec or code) against the 10 Designing for Children's Rights principles, adapted to the child's age band, with a 1-10 scorecard and a prioritized, color-coded issues list in Google Sheets. Use when asked to audit, review or check a kids' product for children's rights, child safety, age-appropriateness or D4CR.
---

# Children's Rights Audit

Audit a digital product for children against the 10 principles of the Designing for Children's Rights guide (44 criteria, in `references/principles.md`). Output: one audit tab in the product's Google Sheet, with a scorecard and a prioritized issues list.

Work in this order. Do not skip intake or the team questions.

## 1. Intake (ask, then wait)

Ask in one message:
1. Product name and a one-line description.
2. Age band(s) of the intended users. Offer the bands in `references/age-bands.md`. If more than one band is chosen, audit against the **youngest** band and note where expectations differ for older bands.
3. Stage: concept / design / built.
4. What you are given: Figma, screenshots, spec/PRD, code, live app (any combination).
5. Link to the product's existing audit Google Sheet, if one exists. If none, a new file is created.

Also remind the user: children may use the product even if they are not the target audience (criterion 2.3). Ask if any younger children are likely users.

## 2. Team-process questions (ask, then wait)

Ask the questions in `references/team-questions.md` in one message. Tell the user they can skip any question. Every criterion that depends on a skipped answer is scored **Not verified**, never guessed.

## 3. Review the product

Read all the input (load the Figma or file tools needed). For each of the 44 criteria:
- Apply the age lens for the chosen band (`references/age-bands.md`).
- Give a score using the rubric below, plus the evidence (screen, component, file, spec section or team answer).
- Mark the **Evidence basis**: `Observed` (seen in design, build or code), `Intent` (from concept, spec or description), or `Team answer`.

### Scoring rubric (1 = completely against the principle, 10 = fully upholds it)

| Score | Meaning |
|---|---|
| 1 | Completely against the principle; actively harms |
| 2-3 | Major gaps; violates it in key places |
| 4-5 | Partial; some support, significant gaps |
| 6-7 | Mostly upholds it; minor gaps |
| 8-9 | Upholds it well; small improvements possible |
| 10 | Fully upholds it; exemplary |
| N/A | Does not apply; a one-line reason is required |
| Not verified | Depends on a team answer that was not given |

Rules:
- **Never invent evidence.** If you cannot see it and the team did not say, it is `Not verified` (team criteria) or scored on what is visible, with the gap noted.
- **Use N/A sparingly.** A missing feature does not make a criterion N/A. Example: no chat does not make principle 5 N/A, because the guide includes in-person play with others.
- **Concept stage:** score the stated intent, mark it `Intent`, and phrase the evidence as "planned", not "done".

### Risk (potential harm to the child)

Default from score: 1-3 High, 4-5 Medium, 6-7 Low, 8-10 None.
**Override:** raise the risk one level (or more) when the consequence is severe, even if the score is fine. This check is required for principle 7 (safety), principle 8 (data) and criterion 9.3 (payments). Example: a 6 on 7.6 (illegal content) is High risk. State the reason in the explanation.

## 4. Issues

Create at least one issue for every criterion scoring 7 or below, and for every overridden risk. Each issue has:
- **Issue:** what is wrong, in one sentence.
- **Explanation:** why it matters for a child of this age, linked to the principle.
- **Principle** and **Criterion ID**.
- **Score**, **Risk**, **Fix effort**, **Priority**.
- **Suggested fix:** concrete and doable, in plain language.
- **Location:** where it occurs (screen, flow, file, spec section).
- **Evidence basis.**

**Fix effort:** `Easy` = copy, UI, settings or defaults change, no new system. `Hard` = new feature, backend or moderation system, data architecture or business-model change.

**Priority** (fix order):
| Priority | Rule |
|---|---|
| P1 | High risk + Easy fix |
| P2 | High risk + Hard fix |
| P3 | Medium risk + Easy fix |
| P4 | Medium risk + Hard fix |
| P5 | Everything else (Low risk) |

Sort the issues by priority, then by score (lowest first).

## 5. Principle scorecard

For each of the 10 principles: the average of its scored criteria (excluding N/A and Not verified, to one decimal place), the **lowest criterion** and its score, the highest risk among its criteria, the counts of N/A and Not verified, and a one-line summary. The lowest criterion is always shown so an average cannot hide a serious failure.

## 6. Output to Google Sheets

Follow `references/sheet-format.md` exactly.
- **Existing file for this product:** add a new tab. Never overwrite earlier tabs.
- **No file yet:** create a spreadsheet named `Children's Rights Audit - <Product name>` and write the first tab.
- **Google Sheets connector not available** (for example in Claude Code): build an .xlsx with the same layout and colors (use the xlsx skill) and tell the user it opens in Google Sheets.

## 7. Chat summary

Keep it short: the overall picture in 1-2 sentences, the top 3 issues (ID, issue, priority), the count of Not verified criteria, and the link to the sheet. Do not repeat the whole sheet in chat.
