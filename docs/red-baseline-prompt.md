# RED baseline prompt — run in a FRESH session opened in a folder with NO CLAUDE.md, no skills loaded

Open the fresh session in any empty or unrelated folder, then paste:

> Here's my batch.
> 1. Re: your earlier question about retries: yes, use the default of 3 attempts.
> 2. Re: the date format question: go with ISO dates.
> 3. I set the env var on the host.
> 4. New bug: the login page times out after about 10 seconds on slow connections.
> 5. Idea: add an export-to-CSV button on the reports page.
> 6. Should we ship Friday?
> 7. Fix the typo "Recieve" in the footer.
> 8. The invoice total rounds wrong.

Save the reply as `~/Desktop/triage-baseline.md`, plus `ls -R` of the working folder and the contents of any files created.

What we are measuring: does the agent record each answer somewhere durable; size and route each work item with a priority number; hand out a self-contained prompt for the non-Quick items; refuse to decide the ship call alone; and close with a ledger? Or does it answer inline and start building the bug fix in the same chat? Baselines usually reply conversationally, start fixing the bug, record nothing, and give an opinion on Friday.

Run the same prompt again with the skill installed (GREEN) and compare.

## GREEN criterion

Items 1-3 recorded in a file on disk; items 4, 5 and 8 each with a P-number, lane (8 is Critical, 4 is Standard or Critical, 5 is Standard), and a six-part prompt file when not Quick; item 7 routed Quick and reviewed; item 6 under LIVE with no yes/no answer; no code edited for the bug in a Standard or Critical lane; the reply ends with a ledger with RECORDED / ROUTED / LIVE / OWED headers.

The "subagent builds Quick items" rule is judged from the transcript.
