# Host adapters

[한국어](USAGE-KR.md) | [Home](../README.md)

**Portability means reusable instruction text, not identical installation support.** The model, host application, and skill loader are different layers. Supplying SANE does not grant file access, rendering tools, or persistence.

## Choose the smallest route

| Host or surface | Route | Important boundary |
| --- | --- | --- |
| ChatGPT web, desktop, mobile; including Astra | Paste `LITE.md` with the task, or attach an entry file and explicitly ask it to be read | This ZIP is not automatically an installed ChatGPT plugin |
| Codex CLI / IDE with local skills | Copy `sane/` to `.agents/skills/sane/`; select it with `/skills` or mention `$sane` | Cloud/app environments need their own accessible copy and host-supported loading |
| Claude web / desktop / mobile | Paste `LITE.md`; use a custom-skill importer only when available in that host | Local Claude Code installation is not automatically every Claude session |
| Claude Code | Copy `sane/` to `.claude/skills/sane/`; invoke `/sane` | Do not overwrite an existing skill without reviewing it |
| Grok or DeepSeek chat apps | Paste `LITE.md` with the actual task | No universal native `SKILL.md` loader is assumed |
| Local AI or another model in a chat runner | Paste `LITE.md`, or append it to a permitted task-specific instruction field | Behavior depends on the runner, context budget, and model; a model file cannot install a skill |
| Generic CLI / IDE agent with file reading | Put the package at a known project path and request a read of `SKILL.md` | A path mention is insufficient when the agent cannot read files |
| API / custom application | Have the application read the chosen file as UTF-8 and send its contents as instructions with the task | Follow that provider's message schema and retain the application's existing policies |

Native path and invocation details were checked against the official [OpenAI and Claude documentation](../references/SOURCES.md). Other rows describe a text-transfer strategy, not verified native integrations. Exact menus, account eligibility, and future versions are not promised.

## Chat and attachment use

Paste the contents, then the task. Do not paste two language versions or both LITE and SKILL. With a readable attachment, an example request is:

```text
Read the attached SKILL.md and apply it to the following UI task.
Use linked references only for a specific issue; if unavailable, use the
entry file's self-contained rules. Preserve the stated scope and brand.
[Your task, source material, constraints, and expected output]
```

The bracketed line is a task placeholder, not a required form. Do not put a persistent interface-design rule into every unrelated conversation. Never upload private source code or datasets without authorization.

## Safe project installation

Run from the project directory containing the extracted **`sane/` source folder**. Choose one destination. These commands copy files only; they do not register cloud plugins or modify global agent policies.

### Bash / POSIX shell: Codex

```sh
if [ -e .agents/skills/sane ]; then
  printf '%s\n' 'Destination exists. Review it before replacing.' >&2
  exit 1
fi
mkdir -p .agents/skills
cp -R sane .agents/skills/sane
```

For Claude Code, replace every `.agents/skills` path in this block with `.claude/skills`. Keep the final folder named `sane`.

### PowerShell: choose a destination

```powershell
# Codex. For Claude Code, use '.claude/skills/sane' instead.
$target = '.agents/skills/sane'
if (Test-Path -LiteralPath $target) {
    throw 'Destination exists. Review it before replacing.'
}
New-Item -ItemType Directory -Path (Split-Path $target -Parent) -Force | Out-Null
Copy-Item -LiteralPath './sane' -Destination $target -Recurse
```

For personal installation rather than project installation, official locations are `~/.agents/skills/sane/` for Codex and `~/.claude/skills/sane/` for Claude Code. Use one scope unless you deliberately manage multiple copies. Confirm discovery in the actual host; start a new session when needed.

### Invocation after installation

Codex:

```text
$sane Repair the attached dashboard's labels and visual hierarchy.
Keep the existing theme, routes, and data. Do not add features.
```

Claude Code:

```text
/sane Repair the attached dashboard's labels and visual hierarchy.
Keep the existing theme, routes, and data. Do not add features.
```

A selector accepting the name is a loading check, not evidence of design quality. Inspect the output separately.

## Astra: thin contract, clear finish

Start with LITE and the concrete deliverable. Preserve decisions already made. Do not require a role-play panel, a full repository tour, repeated self-scoring, a compulsory planning phase, or all reference files before a small change. If more precision is needed, replace LITE with SKILL, or add only the relevant rule section. Do not stack duplicate rules.

Example task addition:

```text
Use the supplied SANE contract for this UI change. Preserve the existing
brand and functionality. Complete the requested implementation, address
known in-scope defects, and state which visual checks were unavailable.
No additional process documents are required.
```

This follows the narrow-scope, on-demand direction in OpenAI's September 11, 2026 guidance, without claiming that Astra cannot use skills. [Source](../references/SOURCES.md)

## Existing project instructions

Do not replace `AGENTS.md`, `CLAUDE.md`, or a runner's system prompt. If a project owner wants a pointer, merge one scoped sentence into the existing instructions using the **real installed path**:

```text
For requested UI work, use <actual-path>/SKILL.md; load references only
for the affected issue. Do not apply it to backend-only edits.
```

`<actual-path>` must be replaced. This package intentionally supplies no auto-loaded root agent file, hooks, permissions, or provider-specific tool declarations.

## Language and maintenance

English is the default native entry point. For Korean, use the `-KR` documents or replace `SKILL.md` with `SKILL-KR.md` in a separate installation copy. Keep `name: sane`, preserve the relative references, and avoid duplicate English/Korean installations. Do not rename the folder to a versioned label without also changing the metadata name.

When updating, compare the installed version before replacing it. Check official host documentation if discovery fails; do not assume every failure is model disobedience. If no loader or file tools are available, return to the pasted LITE route.
