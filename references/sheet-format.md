# Sheet format

## File and tabs
- One spreadsheet per product: `Children's Rights Audit - <Product name>`.
- One tab per audit, named `YYYY-MM-DD · <Stage>` (for example `2026-11-19 · Design`). If the name exists, add ` (2)`.
- Never edit or delete earlier audit tabs.

## Tab layout

**Rows 1-4: header**
- A1: `Children's Rights Audit - <Product name>` (bold, large)
- A2: `Date: <date> | Stage: <stage> | Age band: <band> | Input: <input types>`
- A3: `Scale: 1 = completely against the principle, 10 = fully upholds it`

**Scorecard section** (starts at row 5)
Columns: `Principle` | `Average score` | `Lowest criterion` | `Lowest score` | `Highest risk` | `N/A` | `Not verified` | `Summary`
One row per principle (10 rows). Color the `Highest risk` cell.

**Issues section** (two empty rows after the scorecard)
Columns: `ID` | `Issue` | `Explanation` | `Principle` | `Criterion` | `Score` | `Risk` | `Fix effort` | `Priority` | `Suggested fix` | `Location` | `Evidence basis`
- IDs: `I-01`, `I-02`, ...
- Sorted by priority (P1 first), then by score (lowest first).
- Color the `Risk` and `Priority` cells.

**Criteria detail section** (two empty rows after the issues)
Columns: `Criterion` | `Text` | `Score` | `Risk` | `Evidence` | `Evidence basis`
All 44 criteria, so every score can be traced back.

## Colors (cell background)

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

## Formatting
- Bold, frozen header rows for each section; section titles in bold.
- Wrap text in Issue, Explanation, Suggested fix, Summary and Evidence.
- Column widths: text columns about 300 px, score and ID columns about 80 px.

## Writing to Google Sheets
- Use the Google Sheets connector: create the file (or open it from the link), add the tab, write the values, then apply background colors, bold and wrapping with formatting requests.
- If any write fails, retry once, then fall back to .xlsx.
- .xlsx fallback: same layout, colors and tab name, built with the xlsx skill; name the file `Childrens-Rights-Audit-<product>-<date>.xlsx`.
