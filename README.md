# roman-bandurin.github.io — root catalog site

Static catalog of projects published at `https://roman-bandurin.github.io/`.
Each project is published from its own repository under its own path; this root
site is the directory, not an application.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | Catalog page with links to projects and their agent surfaces |
| `llms.txt` | Short LLM-facing directory (llmstxt.org format) |
| `llms-full.txt` | Full documentation of the catalog |
| `AGENTS.md` | Instructions for agents (including shared-origin storage note) |
| `index.md` | Markdown mirror of the catalog page |
| `sitemap.md` | Structured map of agent-readable surfaces |
| `sitemap.xml` | XML sitemap (root + per-project entries) |
| `robots.txt` | Crawl policy for the whole host, sitemap references |

## Rules

- No build step: all files are served as-is by GitHub Pages.
- No JavaScript applications here — keep this site static and lightweight.
- Per-project documentation lives inside each project path (e.g. `/crypto/llms.txt`);
  do not duplicate project docs at the root — link to them.
- Canonical URL of this site: `https://roman-bandurin.github.io/`.
- When adding a project, update: `index.html`, `llms.txt`, `llms-full.txt`,
  `index.md`, `sitemap.md`, `sitemap.xml`, `robots.txt`.
- Storage note: all paths of this domain share one origin (same
  `localStorage`/`sessionStorage`/cookies). Interactive projects must namespace
  their storage keys by project prefix (see `AGENTS.md`).

## Known limitations (GitHub Pages, static hosting)

- **Content negotiation is not possible.** Serving `text/markdown` for
  `Accept: text/markdown` requests (Agent Ready check P19) requires server-side
  routing; GitHub Pages always returns `text/html` for directory paths. The
  mitigation is explicit `<link rel="alternate" type="text/markdown">` elements
  and direct links to `.md` mirrors.
- **No custom HTTP headers** (e.g. `Link: <...>; rel="describedby"`) — all
  discovery must be expressed in HTML markup.
- **No server-side redirects or rewrites** — every surface must exist as a real
  file at its advertised path.

## Publishing

GitHub Pages serves this repository at the domain root because the repository is
named `roman-bandurin.github.io`. Publish from the default branch root (no build
step required).
