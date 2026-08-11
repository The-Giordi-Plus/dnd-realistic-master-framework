# D&D Realistic Master Framework

A browser-first open framework for building a persistent, realistic AI Dungeon Master for the revised 5e / 5.5e ruleset.

## Core ideas

- persistent campaign state stored in a private GitHub repository;
- tool-based RNG instead of language-model-selected dice;
- no plot armor and no dice fudging;
- autonomous NPCs, factions, quests, deadlines, and world events;
- strict anti-metagaming and knowledge separation;
- Git version history for campaign state;
- separate player-facing and DM-only state;
- no local installation required for the reference setup.

## Status

**v0.1 pre-alpha framework package.**

This repository contains the reusable framework only. Individual campaigns should live in separate private repositories created from the templates.

## Structure

- `regole/` — static AI-DM operating procedures
- `modelli/campaign/` — public empty campaign-state templates
- `modelli/dm/` — empty DM-only state templates
- `gpt/ISTRUZIONI.md` — generic Custom GPT instruction template
- `gpt/AZIONE_GITHUB_OPENAPI.yaml` — generic GitHub Contents API Action schema
- `documentazione/` — setup, architecture, security, licensing, and release notes

## Security

Never commit Personal Access Tokens, API keys, `.env` files, private campaign secrets, or player personal data to a public repository.

Each user should create a **separate private campaign repository** and a fine-grained GitHub token limited to that repository with only the minimum required permissions.

## D&D / SRD compatibility

This project is designed for the revised 5e / 5.5e ruleset and uses **SRD 5.2.1** as its public compatibility baseline. It does not redistribute the Player's Handbook, Dungeon Master's Guide, Monster Manual, or other non-SRD rulebook content.

See `AVVISO.md` and `LICENZA.md`.

## License

This repository uses a split license:
- code/configuration files: MIT;
- knowledge, templates, and documentation: CC BY 4.0.

See `LICENZA.md` for the file-level mapping.
