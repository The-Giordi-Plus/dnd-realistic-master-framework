# D&D Realistic Master Framework

Open-source framework for building a persistent, realistic AI Dungeon Master for D&D 5.5e.

The project is designed around a few core principles:

- persistent campaign state stored in GitHub;
- tool-based random number generation for dice;
- no plot armor or dice fudging;
- autonomous NPCs, factions and world events;
- strict separation between DM knowledge, NPC knowledge and player-character knowledge;
- versioned campaign state with Git history;
- browser-first setup with no local installation required.

## Project status

Early public framework / pre-alpha.

The framework is currently being separated from a private reference campaign before the first public release.

## Planned structure

- `knowledge/` — static operational rules for the AI Dungeon Master
- `templates/campaign/` — player-facing persistent campaign-state templates
- `templates/dm/` — private DM-state templates
- `gpt/` — Custom GPT instructions and GitHub Action schema
- `docs/` — setup, architecture, security and usage documentation

## Important

Do not commit GitHub personal access tokens, API keys, `.env` files, campaign secrets, or private player data.

The repository does not currently include a license. Licensing and SRD attribution will be added after the project content audit.
