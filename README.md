# Children's Rights Audit (Claude skill)

A Claude skill that audits digital products for children (games, apps, sites, concepts, designs, specs or code) against the 10 principles of the **Designing for Children's Rights** guide, adapted to the child's age band.

## What it does
1. Asks for the product, age band, stage (concept / design / built) and input type.
2. Asks short team-process questions (research with children, data, moderation, sustainability). Skipped answers are marked "Not verified", never guessed.
3. Scores 44 criteria from 1 (completely against the principle) to 10 (fully upholds it), with evidence.
4. Writes a Google Sheet tab per audit: a principle scorecard and a prioritized issues list, with color-coded risk and priority, explanations and suggested fixes. Falls back to .xlsx when Google Sheets isn't available.

## Files
- `SKILL.md` - the audit flow, scoring rubric, risk and priority rules
- `references/principles.md` - the 10 principles split into 44 criteria
- `references/age-bands.md` - age bands (from the UK ICO Age Appropriate Design Code) and an audit lens per band
- `references/team-questions.md` - team-process questions
- `references/sheet-format.md` - sheet layout and colors

## Install
Upload the folder as a skill in Claude, or place it in your Claude Code skills folder.

## Credits
- Principles: the Designing for Children's Rights guide (designingforchildrensrights.org). The guide's content belongs to its authors.
- Age bands: UK Information Commissioner's Office, Age Appropriate Design Code, Standard 3.
- Skill design: Inbar Veg Einav.

## License
See [LICENSE](LICENSE).
