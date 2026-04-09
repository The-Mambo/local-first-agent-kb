# Local-First KB Blueprint

A practical blueprint for building a local-first knowledge base for AI assistants.

This repository shows a simple, shareable pattern:
- SQLite + FTS5 for machine-readable search
- plain markdown for human-readable state
- a CLI as the only integration surface for assistants and scripts

The goal is not to prescribe one exact implementation. The goal is to help you
build a similar system in the language, framework, and workflow that fit your
setup.

## Why this exists

Many assistant workflows need a memory layer that is:
- local-first
- searchable
- easy to inspect by humans
- easy to call from an agent
- simple enough to maintain without extra infrastructure

This blueprint is designed to cover that common case before you add embeddings,
external databases, or more complex orchestration.

## What is in this repo

- `docs/LOCAL_FIRST_KB_GUIDE.md` — the full implementation guide
- `examples/skill-wrapper-template.md` — a framework-agnostic assistant skill template
- `LICENSE` — permissive reuse terms

## Core idea

Store the machine-readable index in SQLite, keep human-readable state in plain
markdown, and make a CLI the only stable integration surface.

## Who this is for

- solo builders who want a useful v1 quickly
- small teams building assistant-friendly research or note systems
- people who want a transparent, local alternative to heavier hosted stacks

## What this is not

- not a packaged product
- not tied to one assistant framework
- not dependent on one language or runtime
- not an argument against embeddings forever — just a reminder to start simple

## Read first

Start with the guide:

- `docs/LOCAL_FIRST_KB_GUIDE.md`

Then adapt the example skill wrapper to your own tooling:

- `examples/skill-wrapper-template.md`

## At a glance

```text
Raw source (file / URL / PDF / transcript)
  -> ingest pipeline
  -> SQLite + FTS5 index
  -> CLI
  -> human-readable markdown vault
```

## Sharing and adaptation

If you adapt this pattern for your own system, feel free to fork it, remix it,
and simplify it further. In most cases, a boring local system you understand is
more valuable than a more ambitious stack you cannot easily debug.
