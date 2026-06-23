# openclaw-mem — Session-first memory curator for OpenClaw

> Important knowledge must survive session compaction without bloating the context window. openclaw-mem keeps RAM clean, recall precise, and durable knowledge safe on disk.

[![OpenClaw Skill](https://img.shields.io/badge/OpenClaw-Skill-blueviolet)](https://github.com/NachaFromMars)

## Overview
openclaw-mem v2.1 is a session-first memory system for OpenClaw agents built on one principle: session memory is temporary RAM; disk is the source of truth. It routes durable knowledge to two write targets before compaction occurs. Retrieval always goes through `memory_search` → `memory_get`. Requires session memory indexing to be enabled in OpenClaw config.

## Features
- **Two write targets** — `MEMORY.md` (decisions & preferences) and `memory/YYYY-MM-DD.md` (daily work)
- **Pre-compaction saves** — durable knowledge written to disk before context compaction
- **Retrieval protocol** — always `memory_search` first, then `memory_get` for specific lines
- **Session memory indexing** — enable with: `clawdbot config set agents.defaults.memorySearch.experimental.sessionMemory true`
- **Prevents knowledge loss** — nothing important lost across context boundaries

## Usage / Quick Start
```bash
# Enable session memory indexing
clawdbot config set agents.defaults.memorySearch.experimental.sessionMemory true
```
Then use `memory_search` → `memory_get` for all retrieval. Write important facts before compaction.

## Trigger Keywords (OpenClaw)
save memory, remember this, memory curator, before compaction, openclaw memory, session memory

## Related Skills
- [memory-tiering](https://github.com/NachaFromMars/memory-tiering) — HOT/WARM/COLD tier management
- [infinity-neural](https://github.com/NachaFromMars/infinity-neural) — zero-decay neural memory system

---
Part of the [NachaFromMars](https://github.com/NachaFromMars) OpenClaw skill ecosystem.
