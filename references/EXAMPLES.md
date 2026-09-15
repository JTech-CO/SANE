# Repairs without a fixed template

[한국어](EXAMPLES-KR.md) | [Home](../README.md)

These are original **illustrative examples**, not real product analytics, benchmarks, or a required layout. Preserve the actual task's data and brand.

## E01 - A support dashboard, not a wall of widgets

**Task:** find delayed orders that need action. The existing dark brand, date filter, and order-detail view must remain.

**Bad:** six equally bright KPI cards, a 600px hero plot of total order counts, repeated totals in three regions, a clipped table, and a nonfunctional export icon.

**Repair:** make actionable delayed orders the first working region. Keep the date scope visible. Present the key rate once, beside a valid baseline; put the existing detail view one step away from the relevant row. Reduce or move the historical chart if it adds no value to triage. Remove the fake export affordance rather than adding a new export feature. Use the existing dark palette with clearer semantic emphasis.

**Synthetic comparison fixture:** current period has 14 delayed orders out of 100; the equal-length previous period has 10 out of 100. Definitions and filter scope are identical.

```text
Delayed orders: 14 / 100 (14%)
Previous period: 10 / 100 (10%)
Change in delay rate: +4 percentage points
Relative change in delay rate: +40%
```

Show only the comparison the task benefits from; displaying both changes is not compulsory. Do not label +4 percentage points as +4%. An increase in delay rate is adverse, not automatically a green success arrow. These calculations illustrate S06 and S07, not a recommendation for every KPI.

**Rules:** S01, S02, S04, S05, S07, S08, S09.

## E02 - Sparse data is not a layout bug

**Task:** explore a relationship in four provided observations: `(2, 10)`, `(3, 12)`, `(4, 14)`, `(90, 70)`. Units and labels are supplied by the task.

**Bad:** delete the last observation, crop the range without disclosure, and duplicate the remaining points to make the chart feel full.

**Repair:** preserve all four points. Use a sensible chart size and explicitly labeled axes; put it in the detail region if it is not the primary question. If a transformed scale is justified, make it explicit and preserve interpretability. Show a compact data alternative where the product needs exact lookup. A sparse scatter plot can be the correct representation.

**Do not infer:** that four points establish causality, a reliable trend, or an attractive chart density target.

**Rules:** S04, S06, S07.

## E03 - A Korean editor can keep a common font

**Task:** fix clipping and cramped typography in an English/Korean desktop and mobile writing editor. The existing system sans-serif and dark theme are intentional.

**Bad:** replace the font with an unfamiliar Latin display face, add a metrics sidebar, and shrink Korean toolbar labels to 10px so they remain on one line.

**Repair:** retain the editor canvas as the primary area. Keep the deliberate font choice and verify Hangul fallback. Use a small text/spacing scale, allow labels to wrap or rearrange, and retain working commands. Review mixed text such as `배포 상태 / Deployment status`, `₩1,234,567`, and a long English identifier. Treat a failed custom-font request as a fallback test, not permission to show blank text.

**Rules:** S01, S02, S03, S05, S10. Table-specific checks are not applicable if there is no table.

## E04 - A settings page does not need a hero

**Task:** let a user change notification preferences and save them.

**Bad:** a welcome banner, four usage KPIs, an unrelated activity chart, three equally prominent actions, and decorative toggles that do not change state.

**Repair:** group settings by meaning, preserve their actual values, make each label explicit, and provide a clear working save action with its in-scope feedback. Do not add analytics or new preference categories. A simple form can be the complete, distinctive result.

**Rules:** S01, S02, S03, S06, S08, S10. Chart and statistical-baseline rules may be not applicable.

## E05 - Intentional neon does not excuse weak hierarchy

**Task:** repair a music performance app with an explicitly requested black-and-neon brand.

**Bad:** erase the requested theme and produce a beige admin panel in the name of avoiding AI aesthetics.

**Repair:** preserve the brand, assign stable roles to the neon accents, reserve strong emphasis for the live working state, and improve contrast and label spacing. Distinguish armed, playing, and stopped with text or shape as well as color. Keep essential controls obvious at performance viewing size.

**Rules:** S02, S03, S09, S10.

## E06 - Terminal output is still an interface

**Task:** improve an existing CLI status report, not a web UI.

**Bad:** prescribe a custom webfont, round every row into a card, or rely on red and green ANSI colors alone.

**Repair:** group the summary and actionable failures first, label columns and units, keep long identifiers recoverable, and make plain-text output understandable when color is disabled. Use the terminal's supported behavior and preserve machine-readable output modes. Do not claim to control the user's terminal font.

**Rules:** S01, S02, S05, S06, S07, S08, S09. Web font and CSS measurements are not applicable.

## A bounded repair prompt

```text
Apply SANE only to the attached dashboard's visible typography and labels.
Repair S03 and S06 issues. Preserve the current theme, data, component
behavior, and all unrelated layout. Do not add features or a new font
library. Report any relevant rendered checks you could not perform.
```

A review-only variant should request findings and explicitly say not to edit. For a new build, supply the actual audience and task; do not paste a sample layout as though it were the product's requirements.
