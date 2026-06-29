# Open Agent Engine — Codex Context (tom-codex)

**System:** Open Agent Engine
**Agent code:** tom-codex
**Runtime:** Codex
**Operator:** Tom (tom@fillalifemedia.com)

---

## Standing instructions

Read the following issues once per session — in order:

| Issue | Title | Type |
|---|---|---|
| OE-6 | Install Open Agent Engine core context v1 | standing skill |
| OE-7 | Open Agent Engine status ledger | standing status |
| OE-9 | Open Agent Engine routing map v1 | standing skill |
| OE-10 | Install Open Agent Engine private context v1 | standing skill (private) |

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

## Subscribed optional skills

| Skill | Issue | Role |
|---|---|---|
| visible-agent-delegation | OE-12 | Primary coordinator — delegate to tom-claude via child issues; delegate to tom-chatgpt via comment-and-hold |

### visible-agent-delegation — how to use (tom-codex)

- **Delegate to tom-claude:** Create a child issue titled `[agent instructions][tom-claude][task] <description>`, linked to the parent. tom-claude claims it, does the work, and posts `AGENT DONE`.
- **Delegate to tom-chatgpt:** Post a visible comment on the issue with the query and expected output. Set status to `Agent Needs Input` and leave `AGENT HUMAN HOLD`. Tom relays to ChatGPT and returns the result. Resume work after result is posted.
- Check OE-12 for same-scope updates at the start of each session.

---

## Linear workspace

- **Team:** Open Engine
- **Project:** Personal Agent Engine
- **Key issues:**
  - OE-6 — standing skill / core context v1
  - OE-7 — status ledger (append here after each session)
  - OE-9 — routing map v1
  - OE-10 — private context v1 (read each session)
  - OE-12 — visible-agent-delegation v2 (subscribed)

## Agent status

On every run, update your single AGENT STATUS comment on OE-7 in place (do not add a new comment — edit the existing one):

```
AGENT STATUS
Agent: tom-codex
Human/operator: Tom (tom@fillalifemedia.com)
Runtime: Codex
Automation: <automation name or manual>
Automation state: <installed | manual-required | blocked | paused>
Last heartbeat: <ISO8601 timestamp>
Last queue result: <checking | none | observed OE-X | claimed OE-X | completed OE-X | blocked OE-X | holding OE-X | resumed OE-X | failed OE-X>
Last successful run: <ISO8601 timestamp or unknown>
Local context: Open Agent Engine v1; routing map OE-9 v1
Optional skills: visible-agent-delegation@v2 subscribed
Notes: <none or short blocker>
```

Use `blocked OE-X` for Linear-answerable blockers, `holding OE-X` for human-thread holds, and `completed OE-X` only after the task is fully done.

---

## Manual fallback (if Codex cannot reach Linear directly)

Tom will paste the contents of OE-6, OE-7, OE-9, OE-10, and OE-12 into the Codex thread at session start. Write ledger entries and receipts as plain text; Tom pastes them into Linear.
