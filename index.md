---
title: Roman Bandurin — Projects Catalog
description: Catalog of projects published on GitHub Pages by Roman Bandurin.
last_updated: 2026-10-16
---

# Roman Bandurin — Projects Catalog

This is the root site of `roman-bandurin.github.io`. Each project is published from
its own repository under its own path; this root site is the directory.

## Projects

- [Crypto — Web Crypto API Playground & Agentic Tool Server](/crypto/): browser-based
  cryptography playground (digests, encryption, signatures, key generation) with an AI
  chat and WebMCP tool server. Fully client-side, no backend.
  - [llms.txt](/crypto/llms.txt) — LLM-facing directory
  - [llms-full.txt](/crypto/llms-full.txt) — full documentation
  - [AGENTS.md](/crypto/AGENTS.md) — agent instructions
  - [index.md](/crypto/index.md) — markdown mirror of the app page
  - [openapi.json](/crypto/openapi.json) — API contract

## For agents

- [llms.txt](/llms.txt) — short LLM-facing directory
- [AGENTS.md](/AGENTS.md) — agent instructions
- [sitemap.md](/sitemap.md) — structured map of agent-readable surfaces
- [sitemap.xml](/sitemap.xml) — XML sitemap

## Storage note

All paths of this domain share the same origin and therefore the same
`localStorage`/`sessionStorage`/cookie jar. Interactive projects namespace their
storage keys by project prefix (see [AGENTS.md](/AGENTS.md)).
