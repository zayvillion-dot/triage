# Triage

A Claude Code skill for the moment you hand an agent a pile. A triage session is one chat that takes a mixed batch of inputs (answers to open questions, new findings, ideas, console confirmations, ship calls) and does three things only: record, route, hand out. Without the skill, the agent answers inline, builds the first thing in the same chat, loses the answers, and never ranks the work.

Use it when you dump a mixed batch, say "triage", "here's a batch", or "clear my list", invoke `/triage`, or a tracker shows several ticked or answered items waiting to be applied.

Not for a single isolated task (just do it), a live back-and-forth decision (it gets its own chat), or building a feature (that is what the handed-out prompts are for).

## Install

**As a plugin:**

```
/plugin marketplace add zayvillion-dot/triage
/plugin install triage@triage
```

**Manual:**

Copy `skills/triage/` into `~/.claude/skills/`.

## The pass

| Step | Produces |
|---|---|
| RECORD | Every answer written to its home: progress log, decision notes, tracker. A tick means "do the default as written". |
| ROUTE | Each item sized Quick / Standard / Critical, with a priority number. Quick is done in the session by a subagent. |
| HAND OUT | One self-contained build prompt per Standard or Critical item. |
| LEDGER | Recorded, routed where, what you still owe. |

When the chat slows, it writes `docs/prompts/triage-handoff-latest.md` and prints a paste block for a fresh triage session.

Example ledger:

```
## Triage ledger — 2026-11-01
RECORDED: use the default retry policy -> docs/decisions.md
          env var set on host -> tracker row 4 closed
ROUTED:   P1 login timeout bug -> Standard, prompt docs/prompts/p1-login-timeout.md
          P2 export-to-CSV idea -> Standard, prompt docs/prompts/p2-csv-export.md
          P3 fix typo in footer -> Quick, done here
LIVE:     ship Friday? -> needs one chat with you
OWED BY YOU: confirm staging smoke test (unblocks P1)
```

## Known gaps in 0.1.0

1. No clean RED baseline yet. The prompt for a clean run is in `docs/red-baseline-prompt.md`.
2. Lane sizing is judgment, not measured.
3. No tracker integration beyond a file.

## License

MIT — see `LICENSE`.
