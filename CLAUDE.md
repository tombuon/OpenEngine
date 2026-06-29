# Open Agent Engine — Claude Code Context

---
name: open-agent-engine
description: Route assigned Linear agent tasks through the Open Agent Engine queue.
version: 1
---

Agent code: tom-claude
Human/operator: Tom (tom@fillalifemedia.com)
Linear team: Open Engine
Linear project: Personal Agent Engine
Agent label: agent-instructions
Status ledger issue: OE-7
Optional standing skill directory: OE-8
Subscribed optional skills: none
Private sources: none

---

## Rules

- Process at most one eligible task issue per run.
- Only process issues assigned to Tom.
- Only process issues with the `agent-instructions` label and `[agent instructions]` in the title.
- Only claim task issues whose second title bracket is `tom-claude`, e.g. `[agent instructions][tom-claude][task]`. Standing issues addressed to `[all agents]` still apply.
- Before task work, check mandatory standing context versions assigned to `tom-claude` or `all agents` (currently OE-6).
- Before task work, check only subscribed optional standing skills for same-scope updates.
- Do not browse or install optional standing skills during routine runs.
- When Tom asks what optional skills are available, read OE-8 and summarize relevant options.
- First install/adaptation of an optional standing skill requires Tom's approval in this Claude Code session.
- First approval subscribes this runtime to future same-scope updates for that optional skill.
- Expanded capability, new authority, new tool access, or a runtime change requires fresh approval.
- Claim by moving the issue to **Agent Working** and leaving a comment: `AGENT CLAIMED`.
- Re-read the issue after claiming.
- If complete with no human judgment required, comment `AGENT DONE` and move to **Agent Done**.
- If complete but review, QA, approval, or inspection is required, comment `AGENT DONE` and move to **Agent Review**.
- If blocked and the missing answer belongs on Linear, ask one specific question, comment `AGENT BLOCKED`, and move to **Agent Needs Input**.
- If the question is about local runtime permissions, skill install approval, automation setup, account authority, or private context, ask Tom in this Claude Code session, comment `AGENT HUMAN HOLD`, and move to **Agent Needs Input**.
- Ask before publishing, emailing, posting publicly, deploying, changing billing, changing credentials, deleting destructive data, or making customer-facing changes.

---

## Standing context (mandatory, read each session)

| Issue | Title | Type |
|---|---|---|
| OE-6 | [standing_skill] Install Open Agent Engine core context v1 | standing skill |
| OE-7 | [standing_status] Open Agent Engine status ledger | status ledger |

---

## Receipt format

After every completed task, post a comment on the issue:

```
[receipt] tom-claude | <YYYY-MM-DD HH:MM> | <issue-id>
Did: <one line>
Result: done | partial | blocked
Next: <one line, or 'none'>
Blockers: <one line, or 'none'>
```

## Ledger format

After every work session, prepend a new entry to OE-7 (newest on top):

```
[ledger] tom-claude | <YYYY-MM-DD HH:MM>
Issue: <issue-id or title, or 'n/a'>
Did: <what changed>
Status: done | partial | blocked
Next: <next action, or 'none'>
Blockers: <blocker, or 'none'>
```

---

## Linear MCP

Config: `.claude/settings.json` (uses `LINEAR_API_KEY` env var).
Use `mcp__Linear__*` tools for all Linear interactions.

## Required Linear workflow states

The following custom states must exist in the Open Engine team (create in Linear Settings → Workflow):

| State name | Type |
|---|---|
| Agent Working | started |
| Agent Done | completed |
| Agent Review | started |
| Agent Needs Input | unstarted |
