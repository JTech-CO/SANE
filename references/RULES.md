# Design rules and exceptions

[한국어](RULES-KR.md) | [Home](../README.md)

Read only the rule relevant to the current defect. These are independently written operational rules based on the user's ten failure categories. Numeric defaults below are **SANE design heuristics**, not universal standards. Refer to [SOURCES](SOURCES.md) for provenance and accessibility references.

## S01 - Task before inventory

**Remove:** a screen assembled by adding every available widget, filter, graph, and statistic without a reason to begin anywhere.

**Use:** the user's immediate question or action to choose the first region and information order. For example, exception triage needs the exception list and relevant scope before historical decoration. Put filters near the content they govern and make the active range visible. Keep details available through existing navigation or an in-scope disclosure.

**Check:** someone unfamiliar with the screen can identify what they can learn or do first without opening a manual. A short first-glance check is a design probe, not a validated five-second performance guarantee.

**Exception:** expert monitoring can require several simultaneous signals; editorial or exploratory pages can offer multiple entry points. Define their organizing principle instead of forcing one giant KPI or a sales button.

## S02 - Hierarchy before containers

**Remove:** identical high-contrast cards around every item, nested panels that add no grouping meaning, and several competing primary actions.

**Use:** reading order, scale, placement, grouping, and selective contrast. Repeated peer items may share a component style while their section has a clear place in the page hierarchy. Prefer simple rows, headings, or separators when a card boundary adds no value. A primary working canvas can be the focal region without a headline metric.

**Check:** look at the screen at reduced size or with detail blurred. The intended first region should remain identifiable. Check the actual unblurred UI for readability as well; this probe cannot replace accessibility testing.

**Exception:** equally urgent peers should not receive arbitrary importance. A grid of comparable products or alarms can be correct.

## S03 - A small scale, not a collection of guesses

**Remove:** one-off padding, many almost-identical font sizes, arbitrary corner treatments, text clipped by fixed heights, and essential 10px labels used to fit a layout.

**Use:** existing tokens first. Without a system, start with the compact defaults below and introduce additional tokens only for a clear role. Distinguish hierarchy using weight and spacing as well as size. Allow long labels to wrap; let components grow with content.

**Check:** inventory the type, spacing, and radius roles in the affected surface. Compare computed/rendered results, including chart text and table labels, not only CSS variable declarations. Read the smallest meaningful text at ordinary viewing size.

**Exception:** dense professional tools may need compact secondary text; justify the role and validate it. Do not use compact mode to make the core task unreadable. Native platforms should use their accessible text scales rather than literal web pixel values.

## S04 - Space must serve the task

**Remove:** a large hero chart chosen for spectacle, excessive empty card padding, or a chart that repeats an already clear sentence without adding comparison.

**Use:** the simplest truthful representation for the question. Comparison may need bars; change over time may need a line; exact lookup may need a table. A short statement may be enough. Adjust container height, placement, or representation before changing the data domain. Keep plot labels and visible points readable.

**Check:** ask what decision the dominant region supports, and whether the space would better serve the current task. Do not demand a percentage of filled pixels: sparse distributions and meaningful negative space are valid.

**Exception:** maps, distributions, and uncertainty intervals can contain legitimate empty areas. Keep outliers, missing-data gaps, and meaningful axes. Size-encoding bars should normally start at zero; a nonzero line/scatter domain must stay explicit. Never fake density by duplicating marks or observations.

## S05 - Tables are interfaces

**Remove:** every raw field exposed at once, clipped identifiers, hover-only recovery of essential content, ambiguous headings, and sort icons without actual sorting.

**Use:** a task-relevant default column set and ordering. Put row identity where it remains discoverable. Align comparable numbers consistently; right alignment and tabular numerals are useful when supported. Show units in the appropriate header or cell. Make long content available by wrapping or a keyboard/touch-accessible detail path. Preserve necessary full data; reducing visible columns must not delete information.

**Check:** find a specific record, compare two values, recover a long cell, and operate each displayed sort/filter. Confirm numeric and date ordering use their actual types rather than lexicographic text. On small screens, test the chosen local scroll or alternate layout without reducing essential type.

**Exception:** a genuine raw-data browser may expose many columns. Use deliberate column management and navigation rather than pretending width has disappeared. Do not add search, export, or pagination merely to satisfy this rule when the task does not need them.

## S06 - Meaning belongs near the mark

**Remove:** unexplained 0-9 axes, abbreviations whose expansion is elsewhere, unitless numbers, color-only legends, and core definitions hidden in tooltips.

**Use:** local quantity names and units, recognizable dates, clear categories, and the denominator for rates. Include timezone, normalization, and uncertainty when they change interpretation. Direct labels are useful when they do not collide. Otherwise use a compact, unambiguous legend and accessible alternative.

**Check:** isolate the chart or table from distant subtitles. Can a reader still explain what a value means? Check long English and Korean labels. Keep missing periods distinct from zero; do not silently interpolate absent observations.

**Exception:** a shared label can serve aligned small multiples if the relationship is obvious. Repeating the entire explanation on every point would be worse. Essential interpretation must still be available without hover.

## S07 - Show the signal honestly

**Remove:** a key metric hidden in a secondary label, unsupported trend arrows, manufactured percentage changes, or a comparison that mixes time ranges and filters.

**Use:** the metric that answers the user's question, with a valid baseline, target, or peer where supplied. Explain what changed and the comparison period. Distinguish a percentage-point difference from a relative percent change. Keep definitions and filters aligned. Status descriptions must not rely on color alone.

**Check:** independently recompute displayed derived values from the provided data. Confirm units, rounding, aggregation, and direction of improvement. A lower value is not always worse. Missing history means no computed trend, not a made-up zero baseline.

**Exception:** sometimes the honest result is uncertainty, insufficient data, or several incomparable dimensions. Do not force them into one score or assert causal findings from a correlation.

## S08 - One fact, one primary home

**Remove:** the same total in the header, a progress strip, and a right-side summary when all three communicate the same scope for the same task.

**Use:** one primary placement. Let other regions provide a genuinely new comparison, explanation, or detail. Remove cosmetic filler instead of replacing it with another widget.

**Check:** for each repetition, name the additional user task or context it serves. If there is none, remove or consolidate it.

**Exception:** table totals, local units, active filter scope, independent views, accessible text alternatives, and overview-to-detail continuity are not automatically redundant. Never delete a screen-reader alternative merely because it restates a chart visually.

## S09 - A coherent tone, not an automatic costume

**Remove:** default neon on charcoal, unrelated saturated accents, decorative glows, floating gradient blobs, and glass panels that weaken readability without supporting the intended product.

**Use:** a palette with named roles such as surface, text, muted text, border, action, success, warning, and error. Keep category colors stable between charts and filters. Give decorative effects an explicit brand or interaction purpose. Start with restrained interface emphasis; add categorical or sequential data colors when the data requires them.

**Check:** can each prominent color be explained by a role? Does the interface still communicate state without color? Validate contrast in every supplied theme, not only the default.

**Exception:** a requested game, music tool, retro UI, or cyber-themed product can legitimately be vivid or dark. Preserve its character while correcting contrast, hierarchy, and consistency. A semantic chart palette may need many colors; one-accent minimalism must not erase distinctions.

## S10 - Typography is a decision

**Remove:** selecting the library's default font without checking the product, using monospace for all prose merely to appear technical, and downloading a novelty family solely to avoid familiarity.

**Use:** a coherent typographic direction. Check the title/body relationship, density, weight, numerals, punctuation, and language coverage. A familiar sans-serif or system stack can be the right deliberate choice. For Korean interfaces, test actual Hangul fallback and mixed-script rhythm rather than assuming a Latin family covers both. Prefer licensed, available fonts; this package supplies none.

**Check:** inspect actual loaded and fallback fonts at representative weights. Test long names, Korean sentences, Latin identifiers, numbers, and font-load failure. Distinctive typography should improve fit without slowing or breaking the core reading experience.

**Exception:** platform-native UI, restricted environments, and existing brand systems may intentionally mandate system or common fonts. Preserve them and establish identity through proportion, hierarchy, and layout instead of an unnecessary font change.

## Adjustable starter defaults

These defaults apply only when the project has no suitable system. They are not a mandatory style sheet or a reason to replace valid existing tokens.

| Area | SANE starting point | Boundary |
| --- | --- | --- |
| Body text | `1rem`, commonly 16 CSS px at the browser default | Respect user text settings; never globally shrink the root to evade the baseline |
| Important support text | `0.875rem`, commonly 14 CSS px | Dense nonessential metadata may use 12px after review; not essential labels or an excuse for overflow |
| Type roles | About 4-6 roles; for example 14, 16, 20, 28, 40px equivalents | The count is a coherence probe, not a strict limit |
| Spacing | 4, 8, 12, 16, 24, 32, 48px equivalents | Preserve optical corrections and needed content fit; not every dimension is a spacing token |
| Corner roles | A compact family such as 0, 4, 8px | Pills/circles may have their own semantic role; rounded shapes are not forbidden |
| Reading line height | About 1.5-1.7 for prose | Tune to the selected script, font, and density |
| Font families | One main family; add a second only for a clear role | Coverage fallbacks are not aesthetic family proliferation |
| Interaction targets | Aim for comfortable 44-48px-equivalent hit areas where appropriate | Web WCAG 2.5.8 has a different 24px minimum with exceptions; see REVIEW |

For accessibility thresholds and evidence requirements, consult only the relevant section of [REVIEW](REVIEW.md).
