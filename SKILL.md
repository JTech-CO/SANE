---
name: sane
description: Prevent generic, unreadable UI when creating, redesigning, or reviewing web/app screens and dashboards. Not for backend-only changes.
metadata:
  version: "1.0.0"
  language: "en"
---

# SANE
## Signal Above Needless Embellishment

Remove avoidable confusion, not personality. Treat this as a quality floor, not a visual theme or a prescribed implementation process.

### Scope and authority

Apply to requested interface work: websites, dashboards, mobile/desktop apps, editors, and comparable visual surfaces. For terminal interfaces, translate visual hierarchy into readable text grouping; do not invent CSS requirements. Do not activate for backend-only work or ordinary prose.

Follow the host's instruction hierarchy. Within the authorized task, preserve explicit product requirements, brand decisions, existing design-system tokens, real data, and working behavior. These override SANE's aesthetic defaults, not truthfulness or required accessibility. If they conflict with a readability or access requirement, identify the conflict and use the least disruptive repair.

For a review, report findings without editing. For an edit, repair the requested surface without adding features or redesigning unrelated screens. Infer missing low-risk design details from context; do not block a small task with a questionnaire.

### The minimum contract

Before choosing components, identify the user, their immediate question or action, and what must be noticed first. Reuse context already provided. This is a design decision, not a required planning document. A screen for editing should prioritize the working canvas; a reading page should prioritize reading. Neither needs to become a dashboard.

- **S01 - No inventory-first layout.** Organize information around the task: answer or working area, supporting context, then details. Show relevant scope and filters where they affect interpretation.
- **S02 - No equal-weight everything.** Establish an obvious entry point and distinguish primary, supporting, and background content. Do not put every sentence or metric in an identical bordered card. Equal priority is valid for genuine peers.
- **S03 - No arbitrary scales or tiny essentials.** Reuse a small role-based type, spacing, and radius scale. Start web body text at 1rem and important supporting labels at 0.875rem; these are SANE defaults, not WCAG font-size requirements. Use readable equivalents on other platforms. Never solve overflow by shrinking essential text.
- **S04 - No oversized low-value hero.** Give space to the task, not a chart merely because one exists. Resize, move, simplify, or replace an uninformative chart without changing its meaning. Keep useful whitespace; never crop data, remove outliers, or distort axes to fill a box.
- **S05 - No unreadable data dump.** Give tables useful columns, meaningful ordering, readable headers, units, and an accessible path to necessary detail. Keep full values recoverable. Use local scrolling or another appropriate small-screen presentation, not page-wide clipping. Only show working sort/filter controls.
- **S06 - No contextless labels.** Identify quantities, units, periods, categories, and relevant denominators near the values or axes. Prefer direct labels when they remain legible. Essential meaning must not require a subtitle hunt, color guessing, or hover.
- **S07 - No buried or invented signal.** Make the task's key result directly comparable to a valid baseline, target, or peer when available. Keep scope consistent. Distinguish zero, missing, and loading; label mock data. Do not invent trends or comparisons when data is absent.
- **S08 - No repetition without a new job.** Give each metric one primary home. Repeat only for a different task, necessary local context, accessible alternatives, or overview-to-detail continuity. Remove filler, not useful explanation.
- **S09 - No accidental coding aesthetic.** Use a coherent palette with stable semantic roles and restrained emphasis. Do not default to neon-on-black, decorative gradients, glow, glass, or random chart colors. An explicit brand may use these deliberately. Data categories and statuses may need more than one accent; do not collapse them into one color.
- **S10 - No unexamined typography defaults.** Choose type for audience, language coverage, tone, hierarchy, and reading density. A system font or common family is valid when it fits. Do not replace a good default with a novelty font just to look different. Check Korean/Latin fallback, numerals, wrapping, and actual font loading when applicable.

### Completion boundary

Deliver the requested artifact with readable content, truthful encodings, and working in-scope interactions. Preserve keyboard access, visible focus, accessible names, adequate contrast, and non-color status cues. Keep the essential workflow usable at narrow widths and enlarged text. Respect reduced-motion settings for nonessential motion.

When tools permit, inspect the affected rendered surface and the relevant interaction or state. Check proportionately: a label fix does not require a full redesign or an exhaustive test campaign. Source inspection alone cannot establish visual correctness. Mark unavailable rendering or interaction checks as **not verified**; do not claim to have tested them.

Do not call the result ready while a known blocking defect remains. Fix authorized, in-scope blockers; otherwise deliver what is complete and state the limitation. Follow the user's requested output format. Do not print this contract or create a long compliance report unless asked.

### Optional references

Read only the relevant section when needed, never all files by default:

- [RULES](references/RULES.md): repairs, exceptions, and adjustable numeric defaults.
- [REVIEW](references/REVIEW.md): evidence, accessibility checks, and blocking defects.
- [EXAMPLES](references/EXAMPLES.md): concrete corrections without a fixed page template.

[한국어](SKILL-KR.md)
