# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository status

This repository currently contains only a planning document (`자동제어_이력서_클로드코드_프롬프트.md`) — no `index.html` or other project files exist yet. The repo is not a git repository. When a future session is asked to "proceed" or "start," it means executing the step-by-step plan below, beginning with STEP 1.

## Project goal

Build a single-file HTML resume (`index.html`) for a job candidate in the **자동제어 (industrial automation/control) engineering** field — PLC, SCADA, HMI, instrumentation, control programming. The final deliverable is one self-contained HTML file (CSS/JS inlined, minimal external dependencies) suitable for sharing as a link or printing to PDF for job applications.

## Required output characteristics

These constraints come directly from the project brief and should hold regardless of which step is being worked on:

- **Single file**: everything (HTML/CSS/JS) lives in one `index.html`; avoid external libraries/frameworks or build tooling unless explicitly requested.
- **Responsive**: must work on both desktop and mobile (test down to ~360–480px width). If a two-column (sidebar + main) desktop layout is used, it must collapse to a single column on mobile.
- **Print-friendly**: include `@media print` rules — remove backgrounds/shadows that waste ink, optimize margins for A4, use `break-inside: avoid` so sections don't split across pages, and expose link URLs as visible text when printed.
- **Visual style**: minimal, white-background design with generous whitespace, dark gray body text, and a single navy/blue accent color. Use a system font stack (no web font loading).
- **Semantic & accessible**: use semantic HTML5 tags (`header`, `section`, `article`, etc.), meaningful `alt`/`aria-label` where needed, and sufficient color contrast.
- **Sections carry `id` attributes** for easy incremental styling/editing: header/contact, summary, skills, experience, project highlights, education, certifications, other (awards/patents/languages).

## Workflow (from the prompt guide)

The guide document defines an 8-step incremental workflow — each step should generally be completed and visually verified (open `index.html` in a browser) before moving to the next:

1. **STEP 1** — Scaffold `index.html` structure only (no content yet).
2. **STEP 2** — Add all section markup with placeholder text, each section tagged with an `id`.
3. **STEP 3** — Replace placeholders with real content, ideally section-by-section as the user supplies it (not all at once) for better accuracy.
4. **STEP 4** — Apply the minimal/white/navy visual styling and typography hierarchy; decide between a two-column (sidebar+main) or single-column desktop layout.
5. **STEP 5** — Harden responsive behavior for mobile (360–480px), adjusting font sizes/spacing and layout collapse.
6. **STEP 6** — Add `@media print` styles for clean PDF export.
7. **STEP 7** — Final accessibility/HTML-validity pass (duplicate ids, unclosed tags, contrast, file size) and fix issues found.
8. **STEP 8** — Prepare static-hosting deployment (GitHub Pages / Netlify / Vercel), including any needed config files (e.g. `.gitignore`).

When the user gives an instruction that matches one of these steps loosely (e.g., "이제 스타일링 해줘"), map it to the corresponding STEP's detailed requirements in `자동제어_이력서_클로드코드_프롬프트.md` rather than re-deriving requirements from scratch.

## Working notes

- Content should be requested/incorporated incrementally per section during STEP 3 rather than dumped in bulk — this produces more accurate section-specific results.
- When refining styles, concrete references (hex colors, similar site examples) from the user produce better results than vague requests.
