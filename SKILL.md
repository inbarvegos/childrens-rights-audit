---
name: childrens-rights-audit
description: Audit a digital product for children (game, app, site, concept, design, spec or code) against the 10 Designing for Children's Rights principles, adapted to the child's age band, with a 1-10 scorecard and a prioritized, color-coded issues list in Google Sheets. Use when asked to audit, review or check a kids' product for children's rights, child safety, age-appropriateness or D4CR.
---

# Children's Rights Audit

Audit a digital product for children against the 10 principles of the Designing for Children's Rights guide (44 criteria, in the **Principles and criteria** section below). Output: one audit tab in the product's Google Sheet, with a scorecard and a prioritized issues list.

Work in this order. Do not skip intake or the team questions.

## 1. Intake (ask, then wait)

Ask in one message:
1. Product name and a one-line description.
2. Age band(s) of the intended users. Offer the bands in the **Age bands and age lens** section below. If more than one band is chosen, audit against the **youngest** band and note where expectations differ for older bands.
3. Stage: concept / design / built.
4. What you are given: Figma, screenshots, spec/PRD, code, live app (any combination).
5. Link to the product's existing audit Google Sheet, if one exists. If none, a new file is created.

Also remind the user: children may use the product even if they are not the target audience (criterion 2.3). Ask if any younger children are likely users.

## 2. Team-process questions (ask, then wait)

Ask the questions in the **Team-process questions** section below in one message. Tell the user they can skip any question. Every criterion that depends on a skipped answer is scored **Not verified**, never guessed.

## 3. Review the product

Read all the input (load the Figma or file tools needed). For each of the 44 criteria:
- Apply the age lens for the chosen band (the **Age bands and age lens** section below).
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

For each of the 10 principles: the average of its scored criteria (excluding N/A and Not verified, to one decimal place), the **weakest point** (the lowest-scoring criterion and its score, for example `7.4 Report and block content: 2`), the **highest risk** among its criteria with the counts of N/A and Not verified criteria added to the same cell (for example `Medium · 1 N/A · 2 not verified`), and a one-line summary. The weakest point is always shown so an average cannot hide a serious failure.

## 6. Output to Google Sheets

Follow the **Sheet format** section below exactly.
- **Existing file for this product:** add a new tab. Never overwrite earlier tabs.
- **No file yet:** create a spreadsheet named `Children's Rights Audit - <Product name>` and write the first tab.
- **Google Sheets connector not available** (for example in Claude Code): build an .xlsx with the same layout and colors (use the xlsx skill) and tell the user it opens in Google Sheets.

## 7. Chat summary

Keep it short: the overall picture in 1-2 sentences, the top 3 issues (ID, issue, priority), the count of Not verified criteria, and the link to the sheet. Do not repeat the whole sheet in chat.

---

# Reference sections

## Principles and criteria

Source: the Designing for Children's Rights guide text provided by the user (10 principles). The criteria IDs split each principle into checkable items. The wording stays close to the guide.

Tags: **P** = judged from the product (designs, build, spec, code). **T** = judged from team answers only. **B** = both.

### 1. Gather and respect children's views
UN rights: The Right to Development, The Right to Participate
Guide: Children have the right to participate in their communities and have influence on topics that matter to them.
- 1.1 (T) Ethical research is conducted with children to learn about their views and experiences.
- 1.2 (T) Both the guardian's and the child's consent is obtained for participation.
- 1.3 (T) Children's input is implemented in the design.
- 1.4 (T) Children's friends, parents, teachers and communities are included in the process.
- 1.5 (T) Input from experts in children's well-being, needs and age-specific development, plus up-to-date research from a range of disciplines, is included.

### 2. Everyone can use
UN rights: Non-discrimination
- 2.1 (P) No discrimination by appearance, gender, sex, age, ability, language, ethnicity, nationality or socio-economic background.
- 2.2 (B) Diversity, accessibility and inclusion are supported in all aspects of design, business and marketing practices.
- 2.3 (B) Unintended use is expected, including use by children the product was not designed for.
- 2.4 (P) Spaces and tools are provided for children to build and express a stronger sense of self.

### 3. Use communication children can understand
UN rights: The Right to Information
- 3.1 (P) Children understand all information that could have an impact on them, including terms and conditions and marketing messages, in easy-to-understand language.
- 3.2 (P) Multiple forms of communication (pictures, video, text, sound) on multiple platforms make information understandable and accessible to all.
- 3.3 (P) Communication accounts for age, developmental stage, ability, culture and language.

### 4. Allow and support exploration
UN rights: The Right to Development, The Right to Learn
- 4.1 (P) Children have freedom to experiment, take risks and learn from mistakes.
- 4.2 (P) When mistakes occur, the child is supported to fix them, alone or with an adult.
- 4.3 (P) Curiosity is encouraged; the design considers evolving capabilities by age and development, personality, skills and interests.
- 4.4 (P) Children get opportunities to acquire new skills and take on self-driven challenges.
- 4.5 (P) Children are designed for as creators and contributors, not just consumers.

### 5. Encourage children to play with others
UN rights: The Right to Development, The Right to Participate
Guide: well-being, social life, play, creativity, self-expression and learning can be enhanced by collaborating and sharing with others.
- 5.1 (P) Collaboration and sharing with others are supported.
- 5.2 (P) Safe experiences, online and in person, help develop relationships and social skills.
- 5.3 (P) A healthy social environment: differences that can be used in discriminatory ways are not highlighted.
- 5.4 (B) Design decisions are made with awareness that they shape the culture around the product.

### 6. Create a balanced environment
UN rights: The Right to Development, The Right to Learn, The Right to Leisure and Play
- 6.1 (P) Different moods, views and contexts of play are considered.
- 6.2 (P) Breathing space: interactive and passive time, breaks are encouraged, and offline, social, in-person and tactile experiences are considered.
- 6.3 (P) Children and caregivers can easily set limits, and limits can develop as the child develops.

### 7. Keep children safe and protected
UN rights: The Right to be Protected
- 7.1 (B) The product is safe to use; the team does not assume anyone else will ensure children's safety.
- 7.2 (P) The product explains why something might be unsafe and how to stay safe.
- 7.3 (P) The product helps children improve their digital literacy.
- 7.4 (P) Unwanted and inappropriate content is easy to report and block.
- 7.5 (B) Children have tools to block and distance themselves from unwanted contacts; there is a solid system for reporting and managing users.
- 7.6 (B) Children are not exposed to illegal content.
- 7.7 (P) The behaviour the product encourages is considered, and the environment is healthy.
- 7.8 (P) Caregivers are equipped with an understanding of healthy behaviour.

### 8. Do not misuse children's data
UN rights: The Right to Privacy
- 8.1 (B) No unnecessary data is collected or stored.
- 8.2 (T) A high bar is set for what data is essential to gather.
- 8.3 (P) Children and caregivers keep control over the child's data: choices about what to share and why, and clear information on how it is used.
- 8.4 (B) Children's personal data is not monetized, shared or sold to other parties.
- 8.5 (B) Overall care for children's data and right to privacy is shown.

### 9. Help children recognise and understand commercial activities
UN rights: The Right to Information
- 9.1 (P) Marketing is clearly labelled so children cannot confuse it with information.
- 9.2 (P) It is clearly stated when actions commit children to downloading content or to exclusive use of the product.
- 9.3 (P) Children's understanding of any purchase is confirmed before paying, and parental control for payments is in place.

### 10. Design for the future
UN rights: The Right to Life, The Right to Information
Guide: children have the right to life, a future and a thriving planet; climate and environmental crises are child rights crises.
- 10.1 (P) Children are informed about the root causes, status, effects and systemic nature of climate and environmental crises (where relevant to the product).
- 10.2 (T) The climate and environmental impacts of business operations are considered and measured; negative impacts are reduced and positive ones increased.
- 10.3 (T) Business and design decisions are sustainable and consider long-term effects.
- 10.4 (P) Children and adults are educated to understand their part in caring for the planet together.

## Age bands and age lens

The Designing for Children's Rights guide defines no age bands. These bands and their labels come from the UK ICO Age Appropriate Design Code, Standard 3 (ico.org.uk). The ICO notes that age ranges are not a perfect guide to an individual child, and that other groupings are fine if justified.

The "Audit lens" lines are this skill's own interpretation for auditing. They are not ICO text. Use them as prompts, not as rules.

| Band | ICO label | Audit lens (skill's interpretation) |
|---|---|---|
| 0-5 | Pre-literate and early literacy | Do not rely on text: information must work through audio, icons and visuals. Expect a caregiver to be present: settings, purchases and data choices sit with the adult. Advertising, open chat and purchases that can be reached by tapping are serious concerns. |
| 6-9 | Core primary school years | Early readers: use short, simple words and visual support. Strong defaults and parental controls. Children may not tell ads from content, so 9.1 needs extra care. |
| 10-12 | Transition years | Growing independence and first social features. Digital literacy (7.3) and blocking or reporting tools (7.4, 7.5) become central. Explanations should be addressed to the child, not only the parent. |
| 13-15 | Early teens | More autonomy and peer pressure. The teen should make meaningful privacy choices (8.3). Look for engagement patterns that push compulsive use (6.2, 7.7). |
| 16-17 | Approaching adulthood | Respect autonomy while keeping protections. Treat the teen as the main audience for information and choices; caregiver tools are optional, not controlling. |

## Team-process questions

Ask all of them in one message. Any question can be skipped; criteria that depend on a skipped answer are scored "Not verified".

| # | Question | Criteria |
|---|---|---|
| 1 | Have you done research with children for this product? How, and what ethical safeguards were used? | 1.1 |
| 2 | Did you get consent from both the guardian and the child for research or testing? | 1.2 |
| 3 | Give 1-2 examples of design changes made because of children's input. | 1.3 |
| 4 | Were parents, teachers, friends or communities involved? How? | 1.4 |
| 5 | Which child-development experts or research did you draw on? | 1.5 |
| 6 | List the data you collect from children. Why is each item essential, and how long is it kept? | 8.1, 8.2 |
| 7 | Is any child data shared, sold or used for ads, including through third-party SDKs or analytics? | 8.4, 8.5 |
| 8 | How are reports of content or users handled? Who reviews them, and how fast? How is illegal content prevented? | 7.1, 7.5, 7.6 |
| 9 | How do your business and marketing practices support diversity, accessibility and inclusion? | 2.2 |
| 10 | Have you considered or measured the environmental impact of the product and business (hosting, devices, physical goods)? What did you decide? | 10.2, 10.3 |

## Sheet format

### File and tabs
- One spreadsheet per product: `Children's Rights Audit - <Product name>`.
- One tab per audit, named `YYYY-MM-DD · <Stage>` (for example `2026-11-19 · Design`). If the name exists, add ` (2)`.
- Never edit or delete earlier audit tabs.

### Tab layout

**Rows 1-4: header**
- A1: `Children's Rights Audit - <Product name>` (bold, large)
- A2: `Date: <date> | Stage: <stage> | Age band: <band> | Input: <input types>`
- A3: `Scale: 1 = completely against the principle, 10 = fully upholds it`

**Scorecard section** (starts at row 5)
Columns: `Principle` | `Average score` | `Weakest point` | `Highest risk` | `Summary`
One row per principle (10 rows).
- `Weakest point`: the lowest-scoring criterion as `<ID> <short name>: <score>`, for example `7.4 Report and block content: 2`.
- `Highest risk`: the highest risk level, followed by any unscored criteria, for example `Medium · 1 N/A · 2 not verified`. Leave out the parts that are zero. If no criterion in the principle was scored, write `Not scored · <counts>`. Color the cell by the risk level (grey if not scored).

**Issues section** (two empty rows after the scorecard)
Columns: `ID` | `Issue` | `Explanation` | `Principle` | `Criterion` | `Score` | `Risk` | `Fix effort` | `Priority` | `Suggested fix` | `Location` | `Evidence basis`
- IDs: `I-01`, `I-02`, ...
- Sorted by priority (P1 first), then by score (lowest first).
- Color the `Risk` and `Priority` cells.

**Criteria detail section** (two empty rows after the issues)
Columns: `Criterion` | `Text` | `Score` | `Risk` | `Evidence` | `Evidence basis`
All 44 criteria, so every score can be traced back.

### Colors (cell background)

Risk:
| Risk | Fill | Text |
|---|---|---|
| High | #E06666 (red) | black |
| Medium | #F6B26B (orange) | black |
| Low | #FFE599 (yellow) | black |
| None | #93C47D (green) | black |
| N/A / Not verified | #D9D9D9 (grey) | black |

Priority (blue scale, so it is not confused with risk):
| Priority | Fill | Text |
|---|---|---|
| P1 | #1C4587 | white |
| P2 | #3C78D8 | white |
| P3 | #6D9EEB | black |
| P4 | #A4C2F4 | black |
| P5 | #CFE2F3 | black |

### Formatting
- Bold, frozen header rows for each section; section titles in bold.
- Wrap text in Issue, Explanation, Suggested fix, Summary and Evidence.
- Column widths: text columns about 300 px, score and ID columns about 80 px.

### Writing to Google Sheets
- Use the Google Sheets connector: create the file (or open it from the link), add the tab, write the values, then apply background colors, bold and wrapping with formatting requests.
- If any write fails, retry once, then fall back to .xlsx.
- .xlsx fallback: same layout, colors and tab name, built with the xlsx skill; name the file `Childrens-Rights-Audit-<product>-<date>.xlsx`.

## Credits and license

Copyright (c) 2026 Inbar Veg Einav. All rights reserved. This skill (its structure, instructions, criteria breakdown, scoring rubric and templates) may be used only with the permission of Inbar Veg Einav, and with credit to her. To request permission: inbarvegos@gmail.com

Third-party content keeps its own terms: the principles come from the Designing for Children's Rights guide (designingforchildrensrights.org) and belong to its authors; the age bands come from the UK Information Commissioner's Office Age Appropriate Design Code, Standard 3.
