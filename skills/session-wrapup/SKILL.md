---
name: session-wrapup
description: End-of-session handover. Summarizes what was done, saves durable decisions to memory, and archives a dated log you can search later. Use for /wrapup, "let's wrap up", "save this session", "end of session".
---

# Session wrap-up

Every session ends the same way: write the handover before the context is gone.
Three steps, in this order: memory, summary, archive.

## Step 1: Re-read the session

Go through the whole conversation and pull out:

- **Decisions**: what was decided, and why
- **Done**: what was built, fixed, configured or shipped
- **Learned**: what was not obvious before
- **Open threads**: what is left to pick up
- **Preferences**: how the user wants work done

If nothing durable came up, skip Step 2. Never invent memories to fill the format.

## Step 2: Save to memory

Write durable facts where future sessions will read them:

- Project facts and decisions go in the project's `CLAUDE.md` (or a `docs/decisions.md` it links to).
- Personal working preferences go in `~/.claude/CLAUDE.md`.

Rules:

- Update, don't duplicate. Edit the existing line instead of adding a near-copy.
- Only what the user actually said or decided. No guesses, no command output.
- Absolute dates (2026-10-15), never "last week".
- Skip things that expire on their own: branch names, ports, temporary IDs.
- Never store secrets: API keys, tokens, passwords.

## Step 3: Write the summary

Save it as `sessions/YYYY-MM-DD.md` in the project (add `-2`, `-3` for more sessions on the same day):

```markdown
# Session — YYYY-MM-DD

## Done
- ...

## Decisions
- ... (with the why)

## Learned
- ...

## Open threads
- ...

## Files and systems touched
- ...
```

## Step 4: Archive it somewhere you can ask questions

Pick the first option that is available:

1. **NotebookLM**: add the summary as a "Copied text" source to one permanent notebook (for example "AI Brain"). Months later you can ask "what did we decide about X in September?" and get the answer with the source.
2. **No NotebookLM**: keep the `sessions/` folder in git. `grep -ri "keyword" sessions/` already answers most questions.

If the archive step fails, say so. The summary file and the memory edits are still saved.

## Step 5: Confirm, briefly

- how many memory lines were added or updated
- where the summary was archived (or why it was skipped)
- the open threads to pick up next time

No full re-read of the summary.

---

Made by [@shipwithagents](https://lugiacomo4-star.github.io/shipwithagents/). Short, practical Claude Code breakdowns, tested on real work.
