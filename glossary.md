---
title: Glossary — Roman Bandurin Projects Catalog
description: Terms used across the agent-facing documentation of roman-bandurin.github.io and its projects.
last_updated: 2026-10-17
---

# Glossary

Short definitions of the terms that appear across the agent-facing surfaces of
`roman-bandurin.github.io`. Project-specific terms are defined in the glossary of
the project that uses them.

## Agent discovery

- **AGENTS.md** — plain-Markdown instructions for AI agents working with a site
  or repository ([`/AGENTS.md`](/AGENTS.md)).
- **llms.txt** — short LLM-facing directory in the llmstxt.org format
  ([`/llms.txt`](/llms.txt)).
- **llms-full.txt** — the same format with full documentation instead of a
  directory ([`/llms-full.txt`](/llms-full.txt)).
- **Markdown mirror** — an `index.md` rendition of an HTML page, linked from it
  via `<link rel="alternate" type="text/markdown">`
  ([`/index.md`](/index.md)).
- **Discovery surface** — a non-HTML file an agent is expected to fetch first
  (`llms.txt`, `AGENTS.md`, `sitemap.md`, `index.md`).
- **Citation crawler** — a crawler allowed to quote the page in AI answers;
  permitted here by `max-snippet:-1` and `max-image-preview:large`.

## Agent protocols

- **WebMCP** — W3C in-page MCP surface exposed via `navigator.modelContext`;
  see [`/crypto/.well-known/mcp.json`](/crypto/.well-known/mcp.json).
- **MCP** — Model Context Protocol: a tool-calling convention between a model and
  a tool host.
- **A2A** — Agent2Agent protocol; this site publishes an agent card per project
  ([`/crypto/.well-known/agent-card.json`](/crypto/.well-known/agent-card.json)).
- **agents.json** — wildcard manifest describing chains of agents and tools
  ([`/crypto/.well-known/agents.json`](/crypto/.well-known/agents.json)).
- **agent-permissions.json** — explicit allow-list of client-side operations an
  agent may trigger ([`/crypto/agent-permissions.json`](/crypto/agent-permissions.json)).
- **OpenAPI contract** — machine-readable description of a project's operation
  surface; the root catalog keeps one at
  [`/openapi.json`](/openapi.json), projects keep their own.

## Cryptography (used by the projects)

- **Digest** — a hash of arbitrary input producing a fixed-size value, with no
  key and no reversibility.
- **Symmetric encryption** — encryption and decryption under the same shared key
  (for example AES-GCM).
- **Asymmetric encryption** — encryption under a recipient's public key,
  decryption under the matching private key (for example RSA-OAEP).
- **Digital signature** — a signature created with a private key and verified
  with the matching public key, proving authenticity and integrity.
- **HMAC** — keyed message authentication code built on a hash function.
- **Hex string** — the encoding used for all keys, ciphertexts and digests
  exchanged with agents in this catalog.
- **SPKI / PKCS#8** — ASN.1 structures used to import raw-hex asymmetric keys
  into the Web Crypto API.

## Sitemap

- [Structured map of agent-readable surfaces](/sitemap.md)
- [XML sitemap](/sitemap.xml)
- [Machine-readable catalog contract](/openapi.json)