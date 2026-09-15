# Review and completion checks

[한국어](REVIEW-KR.md) | [Home](../README.md)

Use this when reviewing a UI or confirming a meaningful change. It is not a mandatory ceremony for every edit. Review the affected surface and likely regressions; follow the user's output format.

## Evidence states

Use **PASS**, **FAIL**, **NOT_VERIFIED**, or **NOT_APPLICABLE** for a check. A planned test is NOT_VERIFIED, not PASS. NOT_APPLICABLE requires a reason, such as "this form contains no chart." Do not turn these states into an unvalidated aesthetic score.

Separate evidence from interpretation:

| Evidence | What it can establish | What it cannot establish alone |
| --- | --- | --- |
| Source or DOM inspection | Declared labels, handlers, tokens, structural semantics | Actual visual fit, font loading, readable interaction states |
| Rendered screenshot | Visible hierarchy, clipping, spacing, sampled state | Keyboard behavior, sorting correctness, unseen states |
| Interaction test | The exercised behavior and state transition | Every unexercised route, device, or assistive technology |
| Automated accessibility scan | The rules that the selected tool actually checks | Complete accessibility, product usefulness, or good taste |
| Human/task review | Whether tested users can understand the selected task | Universal usability or statistical certainty without a suitable study |

## Ten-rule check

| Rule | Ask of the actual result |
| --- | --- |
| S01 | Can the intended user identify their first question or action and current scope? |
| S02 | Is the first reading/working priority distinguishable from supporting detail? |
| S03 | Are type, spacing, and corner roles coherent, and is the smallest essential text readable? |
| S04 | Does the dominant region earn its space without distorting data? |
| S05 | Can users identify rows, compare values, recover long cells, and use the displayed controls? |
| S06 | Are quantities, units, periods, and categories understandable locally without hover? |
| S07 | Is the important result visible, correctly derived, and compared only on a valid basis? |
| S08 | Does each repeated fact serve an identifiable additional task or context? |
| S09 | Are palette and state meanings consistent, including across supplied themes? |
| S10 | Does actual typography fit the language, audience, hierarchy, and fallback environment? |

## Web accessibility checks, accurately scoped

These are selected checks, not the whole WCAG standard. Sources are the corresponding W3C Understanding documents in [SOURCES](SOURCES.md).

| Check | Requirement or review boundary |
| --- | --- |
| Text contrast: WCAG 1.4.3 | Normal text: at least 4.5:1. Qualifying large text: at least 3:1. Large means at least 18pt regular (24 CSS px) or 14pt bold (about 18.67 CSS px). Respect the criterion's exceptions. Do not round a failing ratio up. |
| Non-text contrast: WCAG 1.4.11 | Necessary visual information identifying controls, states, and graphical objects generally needs 3:1 against adjacent colors, subject to the criterion's exceptions. This is not a demand that every decorative divider have 3:1 contrast. |
| Text enlargement: WCAG 1.4.4 | Text must resize to 200% without loss of content or functionality, with the criterion's exceptions. A 200% check does not by itself establish reflow compliance. |
| Reflow: WCAG 1.4.10 | Ordinary vertically scrolling web content should work at a width equivalent to 320 CSS px without lost content/function or unnecessary two-dimensional scrolling. Essential two-dimensional regions such as data tables and canvases have exceptions; their surrounding controls and prose do not inherit a blanket exception. |
| Pointer targets: WCAG 2.5.8 | Minimum target size is 24 by 24 CSS px, with spacing, equivalent-control, inline, user-agent, and essential exceptions. SANE's larger comfort target is a design preference, not this minimum. |

SANE additionally expects semantic controls, accessible names, keyboard operation, visible focus, meaningful error text, and non-color status cues. Do not remove focus indication to make the screen cleaner. Avoid unnecessary motion and respect the user's reduced-motion setting. These expectations do not replace a complete platform accessibility assessment.

For native apps, use native accessibility APIs, text scaling, and platform guidance. For terminal interfaces, use readable ordering and plain-text fallbacks rather than claiming CSS-based compliance.

## Proportionate test situations

For a new or substantially changed responsive web screen, inspect a representative desktop view, a narrow view, and the 320 CSS px reflow condition where applicable. Include 200% text enlargement separately. Do not confuse device pixels with CSS pixels. When themes or languages are supplied, inspect the affected theme/language combinations.

Exercise normal data, empty data, loading, error, and long-content states that the component can actually encounter. Check zeros and missing values separately. A single screenshot with ideal sample data is not a regression test. Do not add unrelated UI states to a static page only to manufacture test coverage.

For a small label or spacing repair, check that region, its responsive behavior, and adjacent regressions. A full cross-product matrix is not automatically required.

## Blocking defects versus improvements

**Blocking within the requested scope:** essential text is unreadable or inaccessible; content overlaps or cannot be recovered; a primary in-scope control is fake or broken; units/labels or visual encodings materially mislead; mock data is represented as real; an essential workflow is lost at a supported size or input method; a required accessibility condition fails.

**Improvements, unless they block the task:** slightly uneven emphasis, an unnecessary card border, a weak but readable font choice, nonessential repetition, and modest token drift. Prioritize their effect on users rather than cosmetic rule counts.

Do not mark an output ready with a known in-scope blocker. Fix authorized defects without unnecessary confirmation loops. If a blocker cannot be resolved with the available data or tools, deliver the completed portion, label the limitation, and do not imply a pass.

## Compact review format

Use only when a review is requested. Limit the first pass to the most consequential findings, rather than filling a quota.

```text
Verdict: READY / NEEDS_FIXES / PARTIALLY_VERIFIED
Scope and evidence: [surface, state, viewport, tools actually used]
Finding: [rule ID] [blocker or improvement] [location]
Impact: [what the user cannot read, compare, or do]
Repair: [smallest useful change]
Unverified: [specific missing checks, or none]
```

These verdicts are SANE review labels, not certification. A screenshot-only review should state its interaction limits even when no visual blocker is visible.
