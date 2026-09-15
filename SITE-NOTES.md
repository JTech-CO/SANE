# SANE introduction page

[한국어](SITE-NOTES-KR.md)

A single-file, English-first introduction to **SANE: Signal Above Needless Embellishment**. Prepared on 2026-09-16 from the public SANE 1.0.0 package. The original skill files, repository README, and existing release checksums are not included or replaced.

## Files

```text
index.html
assets/
  og-site.png          # Website social image, 1200 x 630
  og-site.svg          # Matching outlined vector artwork
  og-repository.png    # GitHub repository social image, 1280 x 640
  og-repository.svg    # Matching outlined vector artwork
SITE-NOTES.md
SITE-NOTES-KR.md
SITE-CHECKSUMS.sha256
```

`index.html` contains all CSS, JavaScript, English/Korean text, the complete LITE prompts, and an inline favicon. No installation, build step, framework, analytics, API key, remote font, runtime fetch, or third-party CDN is required. PNG images are for social previews; the visible page does not depend on image loading. Typography deliberately uses locally available Latin and Korean families with system fallbacks. Font binaries are not supplied. The outlined SVG artwork has no external dependencies; its letterforms are editable paths, not live text.

## Deploy without replacing the skill

Copy `index.html` and the `assets/` contents into the **root of JTech-CO/SANE**. Review an existing `index.html` before replacing it. Keep `README.md`, `README-KR.md`, `SKILL.md`, LITE files, references, adapters, tests, and the original `CHECKSUMS.sha256` unchanged. The site notes and `SITE-CHECKSUMS.sha256` are optional deployment companions.

For branch-based GitHub Pages, set **Settings > Pages > Build and deployment > Source > Deploy from a branch**, then select the intended branch and `/ (root)`. An existing Actions-based Pages workflow can instead publish the same static files. No workflow or repository settings have been changed by this deliverable. [GitHub publishing-source documentation](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)

The HTML is configured for the intended deployment base `https://jtech-co.github.io/SANE/`. This is configuration, not a claim that this new page is already deployed. On another domain or project path, replace that complete base URL in the static `canonical`, `og:url`, `og:image`, `og:image:secure_url`, and `twitter:image` tags before publishing. Social crawlers need the publicly reachable image; a local file path is not a substitute. [Open Graph protocol](https://ogp.me/)

The user's concatenated `SANERepo` destination returned 404 through the available repository connection. All primary CTAs therefore target the successfully resolved public repository, [JTech-CO/SANE](https://github.com/JTech-CO/SANE). Update the literal repository URL in both markup and the script constant only if a different destination is actually intended.

## Apply the two OG images

**Website:** `index.html` already points to `assets/og-site.png` through absolute Open Graph and Twitter card metadata. The title, description, dimensions, MIME type, locale, and image alt text are included in the initial HTML.

**Repository:** upload `assets/og-repository.png` through **repository Settings > Social preview > Edit > Upload an image**. Committing an image to the repository does not by itself change GitHub's repository social preview. The supplied opaque PNG is 1280 x 640 and under 1 MB. The SVG is the vector companion, not the GitHub upload format. [GitHub social-preview documentation](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/customizing-your-repositorys-social-media-preview)

Both OG designs are English-first and share the page's ink, restrained red accent, deliberate type hierarchy, and whitespace. They are original typography/vector compositions, not model screenshots or a performance claim. A visitor switching the page to Korean does **not** create a Korean social-card response: a single static HTML response continues to serve English OG metadata. Language-specific crawler responses would require separate static pages or server-side routing and are outside this single-file request.

## Behavior

A first visit without a saved preference opens in English. EN/KR changes the visible copy, document language, document title/description, accessible names, document links, copy payload, and example text. The choice is remembered in `localStorage` under `sane-site-language` where permitted. `?lang=en` and `?lang=ko` override a stored preference. Storage/URL failures are caught; they do not prevent language switching. Only the visitor's language choice is stored.

The Before / With SANE control switches two hand-built interface examples using the same fictional figures. They illustrate prioritization, not actual model output or benchmark results. Sample counts reconcile: 121 on-time + 7 delayed = 128; delayed groups 3 + 4 = 7; $9,420 / 128 rounds to $73.59. The bar is a supporting illustration with the meaning also given in text.

Ten native `details` elements expand the rules. The start section has keyboard-operable Chat & Astra, Codex, and Claude Code tabs. Chat copies the exact complete LITE contract in the selected language; native-agent panels copy an invocation that assumes the package has first been installed. Full installation directions link to the original repository.

Clipboard denial or an unavailable Clipboard API opens a manual-copy dialog with the text selected. No copy success is claimed on failure. Reduced-motion preferences disable smooth scrolling. English content, source links, rules, and the complete English LITE prompt remain available without JavaScript; language switching, comparison controls, tabs, and copy buttons require it.

## Source and maintenance

The page follows the repository [SKILL](https://github.com/JTech-CO/SANE/blob/main/SKILL.md), [README](https://github.com/JTech-CO/SANE/blob/main/README.md), and [host adapters](https://github.com/JTech-CO/SANE/blob/main/adapters/USAGE.md). It is a snapshot, not a live synchronizing client. The embedded EN/KR LITE text was verified against the repository blob IDs:

```text
LITE.md     90e69598aa19e5586d12c8287ba35ced79dd7fc6
LITE-KR.md  20b0b29ec1228018c4f079c7f1ef12f13d523733
SKILL.md    b581fa1c8e8873861ce06cb2e9dc6523550ae3df
```

When LITE changes, update the `sane-lite-source` JSON **and** the static English `lite-preview` content. Preserve the instruction's wording. Recheck both languages and the copy payload. Native loader details are informational links to the original project, not guarantees of support in every future host release. Preserve the SANE repository's existing license and third-party attribution; the source article is not bundled.

## Actual validation

The final run recorded **212 passed checks and zero failures**. Most checks are repeated layout/state combinations, not independent model benchmarks. Rendering and interaction checks used **Chromium 144.0.7559.96** with Playwright document injection (`page.set_content`). Both languages and both comparison states were checked at 320, 360, 390, 768, 1024, 1280, 1440, and 1920 CSS pixels, along with native-agent panels. Root text was enlarged to 200% at 390, 768, and 1440 CSS pixels without page-wide overflow. Desktop/mobile screenshots were visually inspected.

Checked: tab keyboard controls; rule expansion with Enter; real manual-copy dialog selection, Escape, and focus restoration; exact LITE text in both languages; language-dependent links; no-JavaScript fallback; reduced motion; unique IDs and local anchors; zero uncaught JavaScript errors; SVG dependencies; image dimensions, format, and size; and static metadata. Python HTTP reads of the HTML and both PNGs matched the files byte for byte.

Selected foreground/background contrast calculations are below. This is not a complete accessibility audit or certification.

| Pair | Calculated ratio |
| --- | ---: |
| Primary text / paper | 14.46:1 |
| Supporting text / paper | 6.08:1 |
| White CTA text / accent | 5.68:1 |
| Accent text / paper | 5.38:1 |
| Footer supporting text / dark | 9.37:1 |

**Not verified:** the environment returned `ERR_BLOCKED_BY_ADMINISTRATOR` for browser navigation to the tested local HTTP URLs and the local `file://` URL. Browser testing therefore injected the local HTML into a blank document; the Python HTTP checks are not browser navigation checks. Actual Clipboard API writes and native browser storage persistence were not available; their success branches were exercised using explicit test doubles. Real URL navigation, file downloads, other browser engines, physical devices, Pages deployment, GitHub Social preview upload, and external social-crawler collection were not completed. These limits do not stand in for a live post-deployment test.
