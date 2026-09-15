# SANE
## Signal Above Needless Embellishment

**A minimum design contract for AI-generated interfaces.** Keep the signal. Remove avoidable confusion. Keep the product's personality.

[한국어](README-KR.md) | Version **1.0.0** | Reference check: **2026-09-15**

SANE turns ten common dashboard failures into concrete constraints for creating, repairing, or reviewing interfaces. It is English-first, with a complete Korean document set. It is not a UI kit, a fixed aesthetic, an autonomous agent, or a model fine-tune.

## Start with one file

**Any chat interface:** paste the full contents of [LITE.md](LITE.md) before your actual request. This is the lowest-dependency route for ChatGPT, Claude, Grok, DeepSeek, local models, and other text-instruction-capable hosts. A filename alone does not give a model the file's contents.

**File-aware agent:** supply [SKILL.md](SKILL.md) and explicitly request its use. Let the agent retrieve relevant reference sections only when needed.

**Native skill loader:** install the extracted `sane/` folder where the host discovers skills. The entry point is `sane/SKILL.md`. See [host adapters and safe copy commands](adapters/USAGE.md). This is a standalone skill package, not a published ChatGPT plugin or a universal one-click installer.

Choose **LITE or SKILL**, not both, and choose **English or Korean**, not both. Do not load this entire ZIP as compulsory context.

### Example task after the contract

```text
Repair this orders dashboard for a support operator who needs to find
late shipments. Preserve the existing dark theme, dataset, and filters.
Prioritize actionable exceptions and readable comparisons. Do not add
features. Return the changed files and any material verification limits.
```

For Korean, paste [LITE-KR.md](LITE-KR.md) instead. For a Korean native entry point, copy `SKILL-KR.md` over `SKILL.md` in an **installation copy**, retain the folder name `sane`, and keep the references. Do not install two competing entries with the same skill name. This intentional change invalidates the original release checksums for that copy.

## What it removes

| ID | Avoid | Replace with |
| --- | --- | --- |
| S01 | Data and controls without a user journey | A task-led reading or working order |
| S02 | Equal visual weight everywhere | An intentional entry point and hierarchy |
| S03 | Arbitrary scales and tiny essential text | A compact, readable token system |
| S04 | Oversized charts with little task value | Useful space allocation and honest encodings |
| S05 | Clipped, unhelpful data dumps | Scannable tables and recoverable detail |
| S06 | Labels that depend on guessing | Local units, categories, periods, and meaning |
| S07 | Buried key results or invented comparisons | Visible signal with a valid basis |
| S08 | Repetition used as filler | One primary home per fact, useful context retained |
| S09 | Accidental neon coding aesthetics | Coherent brand and semantic color roles |
| S10 | Unexamined font defaults | Deliberate typography and language coverage |

The rule order follows the request that initiated this package, not the source article's original order. Detailed repairs and exceptions are in [RULES](references/RULES.md).

## Deliberately not banned

Dark mode, common fonts, system fonts, cards, whitespace, multiple chart colors, dense expert tools, and explicit retro or neon brands are not automatically wrong. The failure is unexamined choice, unreadability, misleading data, or absence of purpose. Do not turn every product into the same beige minimalist page.

SANE does not require a sidebar, KPI row, hero chart, sales call to action, font download, CSS framework, new dependency, or animation. It adds no analytics, network requests, installation hooks, or executable runtime code. The underlying AI host retains its own permissions and behavior.

## Astra and small-context use

Use **LITE plus the actual task** as the starting point for Astra or any host where a thin contract is preferable. Specify the desired outcome, what must remain unchanged, and the completion boundary. Add a relevant reference only after a concrete issue warrants it. This is a packaging choice, not a claim that Astra ignores skills or that a short prompt guarantees better results. The rationale and current official guidance are linked in [SOURCES](references/SOURCES.md).

## Package map

Every substantive document has an English original and a `-KR` companion.

| File or pair | Read when |
| --- | --- |
| `README.md`, `README-KR.md` | Choosing how to use the package |
| `LITE.md`, `LITE-KR.md` | Pasting a self-contained contract into a conversation |
| `SKILL.md`, `SKILL-KR.md` | Using the full, still compact entry point |
| `adapters/USAGE.md`, `USAGE-KR.md` | Installing or passing instructions to a host |
| `references/RULES.md`, `RULES-KR.md` | Resolving a specific design failure |
| `references/REVIEW.md`, `REVIEW-KR.md` | Checking evidence and readiness |
| `references/EXAMPLES.md`, `EXAMPLES-KR.md` | Seeing concrete repairs and counterexamples |
| `references/SOURCES.md`, `SOURCES-KR.md` | Checking provenance, standards, and adapter sources |
| `tests/ACCEPTANCE.md`, `ACCEPTANCE-KR.md` | Evaluating behavior in your chosen model/host |
| `tests/RELEASE-CHECK.md`, `RELEASE-CHECK-KR.md` | Reviewing this package's actual validation scope |
| `LICENSE.txt`, `LICENSE-KR.md` | Reuse terms and an informational translation |
| `CHECKSUMS.sha256` | Checking archive contents; machine-readable, language-neutral |

## Verification and limits

This release checks its files, links, language pairs, rule coverage, and archive integrity. Behavioral acceptance cases are supplied, not presented as completed multi-model benchmarks. Native skill discovery, visual quality, and model compliance must be evaluated in the target host. Passing a SANE review is not WCAG certification.

The full source and scope of validation are in [RELEASE-CHECK](tests/RELEASE-CHECK.md). Checksum verification on a host with `sha256sum`, from the extracted `sane/` directory:

```sh
sha256sum -c CHECKSUMS.sha256
```

Original package text is provided under the [MIT License](LICENSE.txt). Linked articles, specifications, trademarks, and third-party materials retain their own terms. No third-party screenshots, font binaries, or article copies are bundled.
