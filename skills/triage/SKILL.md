---
name: triage
description: Use when the user dumps a mixed batch of answers, findings, ideas, and confirmations, says "triage", "here's a batch", or "clear my list", invokes /triage, or a tracker shows several ticked or answered items waiting to be applied.
---

# Triage

A triage session takes a mixed batch and does three things only: record, route, hand out. It builds nothing larger than a Quick item.

## The pass

1. **RECORD.** Write every answer to its home: the progress log, the project's decision or memory notes, the tracker. A tick or a one-word reply means "do the default as written". Record it; never reopen an old chat to apply it.
2. **ROUTE.** Size each new item into a lane (table below). Give every routed item a priority number, 1 = first.
3. **HAND OUT.** Write one build prompt per Standard or Critical item (`references/build-prompt-template.md`).

## Lanes

| Lane | Fits | Built by | Where |
|---|---|---|---|
| Quick | One review round: small tweak, one-file fix, tracker edit | A subagent; triage plans and reviews | Inside the triage session |
| Standard | Ordinary feature or multi-file fix | Its own session | Build prompt |
| Critical | Money, pricing, customer-facing documents, login, security | Its own session, full review | Build prompt |

If the lane is in doubt between Standard and Critical, ask.

## Build prompt

Six parts, self-contained: goal, decisions in force, files to read, scope boundary, review tier, report-back line. It must not rely on anything said in the triage chat.

## Live decisions

A ship call or contract term needs back-and-forth. Say so, name it in the ledger, and leave it for one dedicated chat.

## Rollover

When the triage chat slows, write `docs/prompts/triage-handoff-latest.md`, close the session on the tracker, and print the paste block for a fresh triage session.

## Ledger

End every pass with the ledger (`references/ledger-template.md`): recorded, routed where, still owed by the user.

## Common mistakes

| Mistake | Fix |
|---|---|
| Answering inline and not recording | Write each answer to its home first |
| Building Standard work in the triage chat | Route it, hand out a prompt |
| Reopening an old chat for one answer | Record it here |
| Routing without a priority | Number every routed item |
| Build prompt that depends on triage context | Restate decisions and files in the prompt |
| Absorbing a live decision | Flag it for its own chat |
