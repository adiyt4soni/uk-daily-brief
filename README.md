# UK daily brief

A daily job-search command centre: reads email and calendar, syncs every application's status, finds and tiers new roles, prepares applications, and gives exactly three actions for the day.

**Type:** Claude scheduled task · **Area:** Job search automation

## What it does

- Starts a run log and loads a written rulebook, which wins over every other file.
- Reads Gmail and Calendar, saves every employer email and syncs statuses through a validated tool. An interview today outranks every application.
- Sweeps company job boards plus at least three source families live, with raw counts as a positive control (zero postings seen = broken instrument, not an empty market).
- Has subagents read each surviving ad in full and fill an assessment; a script assigns the tier (APPLY / NEAR MISS / ASK / DROP).
- Writes a fixed ten-section brief, newest first, and finishes the run log as ok, partial or failed.

## Guardrails

- Never submits, sends, accepts times, pays or types passwords. It stages drafts and waits for the user's "apply".
- Told to challenge the user, not agree with them: optimise for the offer, not for activity.
- A tool that could not read an account writes BLOCKED; it never reports an empty result.

## When it triggers

> Scheduled daily job-search command centre. Reads Gmail and Calendar, syncs application statuses, sweeps live for roles in scope, tiers them with a written rulebook (APPLY / NEAR MISS / ASK), prepares applications, and issues today's three actions. Never submits on its own.

## What's in this repo

- `SKILL.md`: the skill itself, the file Claude or Codex reads.
- Not included: The rulebook, profile, tracker and every helper script are personal and not published. This repo shows the orchestration prompt with personal details removed.
- Written to be generic: where the skill relies on the user's own files, it names them by role, not by content.

## Install

This is a Claude scheduled-task prompt. Create a scheduled task in the Claude desktop app and paste the body of `SKILL.md` as its prompt, or save it as `~/.claude/scheduled-tasks/uk-daily-brief/SKILL.md`. It expects the project files it names to exist.
