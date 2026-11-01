---
name: triage
description: Use when the user dumps a mixed batch of answers, findings, ideas, and confirmations, says "triage", "here's a batch", or "clear my list", invokes /triage, or a tracker shows several ticked or answered items waiting to be applied.
---

# Triage

A triage pass does three things only: record, route, hand out. It builds nothing larger than a Quick item.

## The pass

1. **RECORD.** Decisions go to the decisions file, status and confirmations to the progress log, items to the tracker (the project's task list file or board; default `docs/tracker.md`). No home? Create `docs/decisions.md` and `docs/tracker.md`. A tick or one-word reply means "do the default as written"; never reopen an old chat. An answer that implies work is recorded AND routed as an item. Details: `references/record-rules.md`.
2. **ROUTE.** Size each item into a lane. Number routed items 1, 2, 3: rank by what unblocks the most work, then by risk.
3. **HAND OUT.** One prompt per Standard or Critical item (`references/build-prompt-template.md`), written to `docs/prompts/<pn>-<slug>.md` and pasted in chat.

## Lanes

Test Critical first.

- **Critical:** touches money, pricing, customer documents, login or security. Own session, full review.
- **Quick:** one file, no behaviour change in a Critical area, not new functionality. A subagent builds it inside the triage session; triage plans and reviews. Commit, merge, or push only after its review passes the repo's hooks.
- **Standard:** everything else. Own session.

Doubt between Standard and Critical: route as Critical and add the question to OWED BY YOU. Do not stop the pass.

## Live decisions

Ship calls, contract or price terms, anything needing back-and-forth: do not answer it; list it under LIVE for its own chat. A tick never closes it. It gets no priority number.

## Rollover

When the user asks, or after three passes, write the handoff file (skeleton in `references/ledger-template.md`), close the session on the tracker, and print the paste block. Write it only then.

## Ledger

End every pass with the ledger (`references/ledger-template.md`) under RECORDED / ROUTED / LIVE / OWED BY YOU.

## Common mistakes

| Mistake | Fix |
|---|---|
| Answering inline, recording nothing | Record first |
| Building Standard work here | Route it, hand out a prompt |
| Routing without a number | Number every routed item |
| Prompt leans on triage chat | Restate decisions and files |
| Answering a live decision | LIVE |
