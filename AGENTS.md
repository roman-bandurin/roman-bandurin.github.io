# AGENTS.md

Instructions for AI agents (browser agents, crawlers, coding assistants) working with
this web site.

> This is the root site of `roman-bandurin.github.io`. It is a static catalog of
> projects; each project is published from its own repository under its own path and
> has its own agent-facing documentation.

## Configuration

- Static HTML, no build step, no backend. All files at the repository root are served
  as-is by GitHub Pages at `https://roman-bandurin.github.io/`.
- Content changes are plain edits to `index.html`, `llms.txt`, `AGENTS.md`,
  `index.md`, `sitemap.md`, `sitemap.xml`, `robots.txt`.

## Usage

- This site is a directory of projects. It does not host application logic.
- Per-project documentation lives inside each project path, for example
  `/crypto/llms.txt` for the Crypto playground.

## Architecture

- `index.html` — catalog page with links to projects and their agent surfaces.
- `llms.txt` — short LLM-facing directory (llmstxt.org format).
- `index.md` — markdown mirror of the catalog page.
- `sitemap.md` / `sitemap.xml` — maps of agent-readable surfaces.

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
