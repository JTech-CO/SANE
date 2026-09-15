# Behavioral acceptance cases

[한국어](ACCEPTANCE-KR.md) | [Home](../README.md)

**Status: NOT_RUN.** These are runnable evaluation briefs, not results. This release has not executed the cases across external models or native skill loaders. The checks of the package itself are separate in [RELEASE-CHECK](RELEASE-CHECK.md).

Use the chosen language's LITE or SKILL once, followed by the case's input and any required fixture. Review the actual artifact, not the model's declaration that it obeyed the rule. For existing-code cases, use a disposable fixture repository, not production.

## Cases

| Case | Input or fixture | Expected observable behavior | Failure to catch |
| --- | --- | --- | --- |
| T01 / S01 | Build a support view for finding delayed orders, with normal and delayed records | The first working region supports delay triage and exposes the selected scope | A generic welcome hero and widget inventory bury the task |
| T02 / S02 | Repair six equal-weight panels; the brief names an exception queue as primary | Exception handling is visibly prioritized while genuine peers remain consistent | Merely recoloring all six cards equally |
| T03 / S03 | Repair a screen with eleven arbitrary type sizes, eight radii, and 10px essential labels | A compact role scale and readable essential labels; long text still fits | Shrinking text, hiding overflow, or adding more near-duplicate tokens |
| T04 / S04 | Use E02's four observations and ask to reduce hero-chart waste | All observations and meaningful axes remain; size/placement changes where useful | Outlier deletion, undisclosed cropping, fabricated points |
| T05 / S05 | A table contains a long Korean identifier, amounts 2/10/100, and a 320 CSS px view | Values are recoverable; numeric sorting is numeric; controls and local overflow work | Lexicographic sorting, clipped identifiers, fake sort controls |
| T06 / S06 | A chart has x ticks 0-9; the source defines x as shipped packages and y as processing minutes | Local axis names and units; essential meaning available without hover | Guessing categories or relying on a distant subtitle |
| T07 / S07 | Current delayed orders 14/100; previous equal period 10/100, same definition/scope | +4 percentage points or correctly labeled +40% relative change, as useful | Calling +4pp "+4%", treating adverse delay as success, mixing scopes |
| T08 / S08 | Repeat one total three times; also provide a text alternative to a chart | Filler repetition is consolidated; accessible alternative retained | Deleting the alternative or retaining all filler under new labels |
| T09 / S09 | Explicitly retain a black/neon music brand and four stable data categories | Brand survives; palette roles and category distinctions become coherent | Replacing the theme with beige minimalism or making categories indistinguishable |
| T10 / S10 | Keep the existing system font in a Korean/English editor; repair clipped labels | Font decision preserved, actual fallback and wrapping checked where possible | A novelty Latin-only font or claiming unchecked font rendering passed |
| T11 / scope | Build a notification-settings form with no analytics requirement | A working settings flow without invented KPIs/charts | Turning every UI into the same dashboard template |
| T12 / non-trigger | Fix a backend-only parser's date handling, no interface change | SANE does not initiate design work or demand visual QA | Loading a design workflow and changing unrelated UI |
| T13 / review only | Review an attached screenshot; explicitly do not edit files | Findings tied to visible evidence; interaction limitations disclosed | Editing code or claiming keyboard/sorting tests from a screenshot |
| T14 / evidence | Provide source only, with no renderer or browser tools | Source findings and clear NOT_VERIFIED visual/interaction status | "Tested on mobile" or "visually verified" without execution |
| T15 / missing data | Ask for a historical trend but supply only one period | Trend unavailable or a request for the missing basis; no invented baseline | Fabricated history, zeros substituted for missing periods, unlabeled mock data |
| T16 / bounded repair | Request only a mislabeled axis be fixed in an approved UI | The label and any directly affected wrapping change; unrelated design remains | New dependencies, a complete rebrand, mandatory long planning documents |

E02 is in [EXAMPLES](../references/EXAMPLES.md). For T15, distinguish asking for necessary missing analytical data from blocking a low-risk styling repair with questions.

## Running a meaningful comparison

Keep task inputs, fixture data, host, model version, accessible tools, viewport, and relevant generation settings the same. Compare a baseline request with a request containing SANE. Record whether the entry file actually loaded. Repeat runs when practical and report variability; one favorable example does not establish general improvement.

Record per applicable case: loading route, rule IDs, observed evidence, PASS/FAIL/NOT_VERIFIED/NOT_APPLICABLE, and any in-scope blocker. A host without rendering tools may pass instruction-delivery checks while visual quality remains unverified. Exclude inapplicable cases transparently; never count them as successes.

The acceptance criterion is observable task/readability improvement with preserved data, scope, brand, and behavior. It is not the number of prohibitions repeated in the answer or the length of a self-review.

## Compact run record

```text
Host / model / version:
Contract: LITE or SKILL; EN or KR; package version:
Loading route and evidence:
Case / source fixture / viewport or terminal width:
Observed result and evidence:
Status: PASS / FAIL / NOT_VERIFIED / NOT_APPLICABLE
Blocking defect, if any:
Regression or scope violation, if any:
```

No installed-host success or cross-model performance claim should be added to the README until a corresponding run record exists.
