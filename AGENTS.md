# Open Agent Engine — Codex Context (tom-codex)

**System:** Open Agent Engine  
**Agent code:** tom-codex  
**Runtime:** Codex  
**Operator:** Tom (tom@fillalifemedia.com)

---

## Standing instructions

Read Linear issue OE-6 ([agent instructions][all agents][standing_skill] Install Open Agent Engine core context v1) once per session. It is the canonical source of standing behavior for all agents.

Summary of standing behaviors:

1. **Post a receipt** after every task (comment on the Linear issue):
   ```
   [receipt] tom-codex | <YYYY-MM-DD HH:MM> | <issue-id or title>
   Did: <one line>
   Result: done | partial | blocked
   Next: <one line, or 'none'>
   Blockers: <one line, or 'none'>
   ```

2. **Append to the ledger** (OE-7) after every work session — newest entry on top:
   ```
   [ledger] tom-codex | <YYYY-MM-DD HH:MM>
   Issue: <issue-id or title, or 'n/a'>
   Did: <what changed>
   Status: done | partial | blocked
   Next: <next action, or 'none'>
   Blockers: <blocker, or 'none'>
   ```

3. **Routing:** All work is owned by Tom. If blocked, mark `blocked` — do not reassign.

---

## Linear workspace

- **Team:** Open Engine
- **Project:** Personal Agent Engine
- **Key issues:**
  - OE-6 — standing skill / core context v1
  - OE-7 — status ledger (append here after each session)
