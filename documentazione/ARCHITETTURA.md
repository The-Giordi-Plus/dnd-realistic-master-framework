# Architecture

The framework separates three concerns:

1. **Static operating rules** — loaded into the AI assistant as Knowledge.
2. **Dynamic campaign state** — stored in a separate private GitHub repository.
3. **Randomness/tool execution** — handled by Code Interpreter/Data Analysis or another reliable RNG tool.

## State model

Player-facing canonical state:
- `campaign/PG.md`
- `campaign/STATO_CAMPAGNA.md`
- `campaign/NPC_CAMPAGNA.md`
- `campaign/QUEST.md`
- `campaign/CRONOLOGIA.md`

DM-only state:
- `dm/SEGRETI_DM.md`
- `dm/FAZIONI_INTERNE.md`
- `dm/EVENTI_PENDENTI.md`

Git history provides versioning and rollback. Chat memory is never treated as the sole authoritative persistent store.
