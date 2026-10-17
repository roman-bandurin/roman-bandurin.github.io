# AGENTS.md

Instructions for AI agents (browser agents, crawlers, coding assistants) working with
this web site.

> This is the root site of `roman-bandurin.github.io`. It is a static catalog of
> projects; each project is published from its own repository under its own path and
> has its own agent-facing documentation.

## Configuration

- Static HTML, no build step, no backend. All files at the repository root are served
  as-is by GitHub Pages at `https://roman-bandurin.github.io/`.
- Content changes are plain edits to `index.html`, `llms.txt`, `llms-full.txt`,
  `AGENTS.md`, `index.md`, `glossary.md`, `openapi.json`, `sitemap.md`,
  `sitemap.xml`, `robots.txt`.
- `.nojekyll` at the repository root is required: without it GitHub Pages runs
  Jekyll, which converts Markdown files that carry YAML frontmatter (for example
  `index.md` and `glossary.md`) into HTML instead of serving them verbatim.
- `openapi.json` is intentionally published at the root: it describes the catalog's
  own static surfaces, so agents discover the contract before descending into a
  project. Project contracts live under their own path (`/crypto/openapi.json`).

## Usage

- This site is a directory of projects. It does not host application logic.
- Per-project documentation lives inside each project path, for example
  `/crypto/llms.txt` for the Crypto playground.

## Architecture

- `index.html` — catalog page with links to projects and their agent surfaces.
- `llms.txt` / `llms-full.txt` — LLM-facing directory and full documentation
  (llmstxt.org format, absolute URLs).
- `AGENTS.md` — this file.
- `index.md` — markdown mirror of the catalog page.
- `glossary.md` — glossary of the discovery, protocol and cryptographic terms used
  across the catalog and its projects.
- `openapi.json` — OpenAPI 3.1 contract of the catalog's static surfaces.
- `sitemap.md` / `sitemap.xml` — maps of agent-readable surfaces.
- `robots.txt` — crawler policy for the whole host, including project paths.

## Sitemap

- [sitemap.md](/sitemap.md): structured map of every agent-readable surface
- [sitemap.xml](/sitemap.xml): XML sitemap with `lastmod` dates
- [glossary.md](/glossary.md): glossary of terms
- [openapi.json](/openapi.json): machine-readable catalog contract

## Projects

### /crypto/ — Crypto — Web Crypto API Playground & Agentic Tool Server

- URL: `https://roman-bandurin.github.io/crypto/`
- Client-side cryptography playground with AI chat and WebMCP tools. No backend.
- Agent docs: `/crypto/llms.txt`, `/crypto/llms-full.txt`, `/crypto/AGENTS.md`,
  `/crypto/index.md`, `/crypto/openapi.json`, `/crypto/sitemap.md`.

## Storage note (for the future)

All paths of `roman-bandurin.github.io` share the same origin, therefore the same
`localStorage`, `sessionStorage` and cookie jar. If two projects ever use the same
storage keys, they will silently overwrite each other's data. When adding a second
interactive project, namespace its storage keys by project prefix (for example
`crypto:*`) — this prevents collisions but does not create a security boundary.
