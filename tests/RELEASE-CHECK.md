# Release validation

[한국어](RELEASE-CHECK-KR.md) | [Home](../README.md)

Version **1.0.0**. Prepared and checked **2026-09-15**.

## Contents

The release contains **22 text documents in 11 English/Korean pairs**, plus `CHECKSUMS.sha256`: **23 files** inside one `sane/` root folder. The checksums cover every text document and intentionally do not include the checksum file itself.

`SKILL.md` is **53 lines** and **855 whitespace-separated words**, including metadata and headings. `LITE.md` is **18 lines** and **273 whitespace-separated words**, including its heading. These are file measurements, not model token counts. Korean sizes differ; no claim of identical token usage is made.

## Executed package checks

| Check | Result | Evidence scope |
| --- | --- | --- |
| UTF-8, LF newlines, final newline, no replacement characters | PASS | All text documents |
| English/Korean companion presence | PASS | All 11 document pairs |
| Rule/case/example/source identifier parity | PASS | Corresponding identifier sets across language pairs; not automated proof of translation quality |
| Core metadata | PASS | YAML parsed; `name: sane` matches the parent folder; field lengths and string metadata checked |
| Core size | PASS | Both entry documents are below 500 lines |
| Rule coverage | PASS | S01 through S10 present in both core, LITE, rulebook, review, and acceptance documents |
| Acceptance-case coverage | PASS | T01 through T16 supplied in both languages, explicitly NOT_RUN |
| Relative Markdown links | PASS | Every parsed local file link resolves inside the package |
| Markdown parsing and fences | PASS | Parsed with markdown-it-py, including tables; fenced blocks balanced |
| Documented POSIX copy procedure | PASS | Executed in disposable directories for both adapter paths; existing-destination protection exercised |
| Unrequested binaries and runtime code | PASS | No font binaries, executables, installation hooks, or runtime scripts bundled |
| Checksums and ZIP round trip | PASS | SHA-256 file checks, ZIP integrity test, safe paths, and byte comparison after archive reading |

Core metadata was checked locally against the published format constraints. This is not an official validator certification or a live host installation test. Markdown parsing is not a browser visual-layout test.

## Not executed or established

PowerShell examples were not executed. Codex, Claude Code, ChatGPT, Grok, DeepSeek, and local-model hosts were not launched to load this package. No multi-model benchmark, rendered sample application, native-app accessibility test, or proof of improved design quality was produced. The [behavioral cases](ACCEPTANCE.md) remain **NOT_RUN**.

Public reference documents were reviewed for the source and adapter notes. Their existence does not prove live availability for every account, platform, version, or installed environment.

Package validity and instruction portability are distinct from model obedience and visual quality. Do not convert this report into a claim that SANE guarantees attractive, accessible, or identical output from every AI.
