# Ledger template

End of every pass:

```
## Triage ledger — <date>
RECORDED: <answer> -> <file or tracker row>
ROUTED:   P1 <item> -> Standard, prompt <path>
          P2 <item> -> Quick, done here
LIVE:     <decision needing its own chat>
OWED BY YOU: <item> (unblocks P<n>)
```

# Triage handoff file skeleton

`docs/prompts/triage-handoff-latest.md`

```
# Triage handoff — <date>
Open items: <ranked list with lanes>
Prompts handed out: <paths, status>
Pending answers: <what is waiting on the user>
Live decisions open: <list>
Tracker: <path>; session closed: <yes/no>
Paste to start: "Fresh triage session. Read <this file>, then the tracker."
```
