# RED baseline prompt — run in a FRESH session opened in a folder with NO CLAUDE.md, no skills loaded

Open the fresh session in any empty or unrelated folder, then paste:

> Here's my batch.
> 1. Re: your earlier question about retries: yes, use the default of 3 attempts.
> 2. Re: the date format question: go with ISO dates.
> 3. I set the env var on the host.
> 4. New bug: the login page times out after about 10 seconds on slow connections.
> 5. Idea: add an export-to-CSV button on the reports page.
> 6. Should we ship Friday?

Save the reply as `~/Desktop/triage-baseline.md`.

What we are measuring: does the agent record each answer somewhere durable; size and route each work item with a priority number; hand out a self-contained prompt for the non-Quick items; refuse to decide the ship call alone; and close with a ledger? Or does it answer inline and start building the bug fix in the same chat? Baselines usually reply conversationally, start fixing the bug, record nothing, and give an opinion on Friday.

Run the same prompt again with the skill installed (GREEN) and compare.
