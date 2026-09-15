# Sources and interpretation boundaries

[한국어](SOURCES-KR.md) | [Home](../README.md)

Reference check: **2026-09-15**. URLs describe the versions reviewed for this release; host behavior may change. Linked materials are not bundled, relicensed, or presented as endorsements.

## Origin

**R01. Adam Kucharski, September 2, 2026.** [Ten reasons your vibe-coded dashboard looks terrible](https://kucharski.substack.com/p/ten-reasons-your-vibe-coded-dashboard).

The user supplied a Korean ten-point summary and requested an operational design contract. That summary is the immediate input to SANE; the article was checked for provenance and context. SANE is an independent adaptation, not a translation or reproduction of the article. The article's aesthetic judgments are not scientific proof that a font family, dark mode, or all AI-generated dashboards are bad.

The user's order is preserved: S01=article 1, S02=2, S03=10, S04=3, S05=4, S06=5, S07=6, S08=7, S09=8, S10=9.

## Packaging and host behavior

**R02. Agent Skills.** [Specification](https://agentskills.io/specification).

Basis for a lowercase matching folder/name, YAML `name` and `description`, a `SKILL.md` entry point, and optional on-demand references. Format conformance is not a guarantee that every host implements the format.

**R03. OpenAI.** [Build skills](https://developers.openai.com/codex/skills/), redirected when checked to [ChatGPT Learn](https://learn.chatgpt.com/docs/build-skills).

Basis for the documented Codex `.agents/skills` locations and `$`/`/skills` selection. The documentation distinguishes standalone skills from plugin distribution. This release does not publish or install a ChatGPT plugin.

**R04. Anthropic.** [Extend Claude with skills](https://code.claude.com/docs/en/skills).

Basis for Claude Code's project/personal `.claude/skills` paths and `/sane`-style invocation. Other Claude surfaces may use different loading and account settings.

**R05. OpenAI, Eric Provencher, September 11, 2026.** [Rethinking skills and prompts for GPT-6 Astra](https://learn.chatgpt.com/blog/rethinking-skills-and-prompts-for-gpt-6-astra).

The guidance favors narrowly scoped descriptions, on-demand resources, and avoiding unnecessary procedural scaffolding. SANE's LITE route is a design response to that guidance, not an empirically established optimal prompt for Astra or an assertion that skills are obsolete.

## Accessibility references

The following are W3C's **Understanding** explanations of specific WCAG 2.2 criteria. They support the selected numerical checks in REVIEW; they are not a substitute for the complete normative standard or a conformance assessment.

**R06. W3C.** [Understanding SC 1.4.3: Contrast (Minimum)](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum.html). Text contrast ratios and the large-text distinction.

**R07. W3C.** [Understanding SC 1.4.11: Non-text Contrast](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast.html). Relevant controls, states, and graphical information; not every decorative border.

**R08. W3C.** [Understanding SC 1.4.4: Resize Text](https://www.w3.org/WAI/WCAG22/Understanding/resize-text.html). The 200% text-enlargement check and its scope.

**R09. W3C.** [Understanding SC 1.4.10: Reflow](https://www.w3.org/WAI/WCAG22/Understanding/reflow.html). The 320 CSS px condition and essential two-dimensional layout exceptions.

**R10. W3C.** [Understanding SC 2.5.8: Target Size (Minimum)](https://www.w3.org/WAI/WCAG22/Understanding/target-size-minimum.html). The 24px target criterion and exceptions; distinct from a larger comfort target.

## Interface and data-visualization guidance

**R11. IBM Carbon Design System.** [Axes and labels](https://carbondesignsystem.com/data-visualization/axes-and-labels/).

Supports explicit quantities/units, truthful axis choices, recognizable time increments, and visible missing-data gaps. Empty plot area is not, by itself, a reason to change observations or distort an axis.

**R12. IBM Carbon Design System.** [Data table: usage](https://carbondesignsystem.com/components/data-table/usage/).

Reference for structured tabular interaction and choosing useful table capabilities. SANE does not require adopting Carbon, its theme, or every optional table feature.

**R13. GOV.UK Design System.** [Typeface](https://design-system.service.gov.uk/styles/typeface/).

An example of typography governed by service context and brand eligibility rather than novelty. It is not a license to redistribute GDS Transport, and SANE includes no fonts.

## License reference

**R14. SPDX.** [MIT License](https://spdx.org/licenses/MIT.html).

Reference for the license text used for newly written package material. The Korean license document is informational; the English license controls. External materials retain their own terms.

## What is SANE's own judgment?

The 1rem/0.875rem starting sizes, compact token counts, sample spacing/radius scales, larger comfort targets, first-glance probes, blocker classification, and acceptance cases are original adjustable project conventions. They are not quoted WCAG requirements or evidence that one aesthetic is objectively superior.

The portable paste route is an instruction-delivery pattern. No benchmark establishes identical behavior across ChatGPT, Codex, Claude, Claude Code, Grok, DeepSeek, or local models. Native integration status outside the specifically documented adapters is deliberately not asserted. See [release validation](../tests/RELEASE-CHECK.md).
