# Copilot / AI Agent Instructions

Purpose: Quickly onboard AI coding agents to this repository — a small, static developer portfolio.

Big picture
- Single-page static site: the app is delivered as two primary files: [index.html](index.html) (content + tiny inline JS) and [styles.css](styles.css) (all styling).
- No build system, package manager, or tests are present. Changes are deployable by editing files and uploading to a static host.

Key patterns & examples
- Content structure: `header.container.fade-up`, main sections `.about`, `.skills`, `.projects`, and `footer` in [index.html](index.html).
- Animation pattern: elements with class `fade-up` become visible via an IntersectionObserver defined in the inline script at the bottom of [index.html](index.html).
- CSS conventions: color and theme variables are in `:root` in [styles.css](styles.css). Layout utilities: `.container`, grid layouts `.skills-grid` and `.project-grid`, and card components `.skill-card` / `.project-card`.

Developer workflows
- Quick preview (no build): run a static server from the repo root and open http://localhost:8000
  - Python: `python -m http.server 8000`
  - Node (optional): `npx serve .` or `npx http-server`
- Editing guidance: change text and structure in [index.html](index.html); update presentation in [styles.css](styles.css). Keep CSS variables in `:root` for theme edits.

Project-specific conventions
- Keep all visual/layout styles in [styles.css](styles.css); avoid adding inline styles in HTML unless tiny helper styles are necessary.
- Reuse existing class names and structure: adding new project cards should follow the `.project-card` markup and include a `.stack` span for tech labels.
- The page uses Russian (`lang="ru"`) content; preserve language metadata unless intentionally changing localization.

Integration points & external dependencies
- There are no external build/deploy integrations inside the repo. Project descriptions mention backend tech (C#, .NET, WPF, PHP, databases) but those systems are not included here.

When making changes
- Prefer non-destructive edits: add new sections below existing ones and test locally with a static server.
- If adding JS, keep it unobtrusive and follow the existing pattern (vanilla JS; small, inline or external file placed before `</body>`).

What not to do
- Do not introduce a build toolchain or package management files without asking the repo owner.
- Do not remove the IntersectionObserver animation — many layout cues rely on `.fade-up.visible`.

Next steps for contributors
- For content updates: edit [index.html](index.html).
- For style/theme updates: edit [styles.css](styles.css).
- Ask the repo owner if you plan to add CI, tests, or server-side components.

If anything here looks incorrect or you'd like more detail (example edits, PR checklist, or deployment notes), tell me which parts to expand.
