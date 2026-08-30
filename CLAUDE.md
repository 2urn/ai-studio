# ai-studio — working instructions

Loaded automatically by any Claude Code session opened in this folder.

> **This file starts nearly empty and that is correct.** It is not documentation.
> It is the place where things that cost an evening get written down so they cost
> an evening once. Add to it when something surprises you, not when you set up.
> `radi/CLAUDE.md` reached 383 lines and `arena/CLAUDE.md` reached 1,307 that way —
> neither was written up front.

## What this repo is

**The broadside for the talk on inviting AI into the studio** — given outside the
FIU context, which is why it is the most fully branded of them.

**It is also the origin of the method.** `radi/SHARED.md` names the pattern that most
of the catalogue now has:

> *A broadside that works. It teaches something worth knowing, lets you try it on your
> own material while you read, and hands you back something you can use somewhere
> else.*

That description was reverse-engineered from this talk. Trademarker, Namer, Brander,
Landing Pager and Poster are all scaffolded against it. **This is the first instance
of a form that now has five descendants**, and it should say so.

Public by design. See LICENSE — attribution, no derivatives.

Remote: `git@github.com:2urn/ai-studio.git`

## Who you're working with

An artist, teacher and designer — real front-end experience in his past, not a
professional programmer. He dictates his messages, so expect transcription
artefacts and read for intent.

**He is observant and his bug reports are accurate.** When he says something is not
working, it is not. Do not close a report as a false alarm; check three places and
report what you checked rather than contradicting him.

**He works in the Claude Mac app, not a terminal.** An answer that resolves to
"open a terminal and type this" is a failure of the tooling.

**Lead with the headline.** He skims. Put the decision-changing fact in line one.

**Only ask when a question is both expensive AND unpredictable** — both, not either.
Cheap or predictable calls get made, then reported. When you do ask, ask as a
multiple-choice question; he is often driving.

**Separate what was verified from what was inferred.** Never blend them into one
confident number.

## Conventions

- **One folder per thing, named after the thing.**
- **Re-runnable scripts in `Modules/`**, not remembered steps. If a task needs
  repeated judgement, build the instrument before the feature — it nearly always
  pays back in the same session.
- **Name the purpose, not the mechanism.** A control named after how it works makes
  the tool feel arbitrary.
- **Say what is wrong AND how to fix it.** "Short by 3 — raise a capacity or drop
  the floor" beats "invalid configuration".
- **State the arithmetic impossibility before the output**, rather than producing a
  result with quiet holes in it.

## Commit and push, and write the commit like it will be read

Commit after each working change and push. Git is the safety net; a mis-save is a
`git checkout` away.

**`HISTORY.md` is generated from the log** by `python3 Modules/history.py`, so the
commit messages ARE this project's written history. That is deliberate: a hand-kept
changelog is a second record of the same events and the two diverge the first time
somebody is in a hurry.

So write the message with the reasoning in it — what broke, what was *measured*,
why a decision went the way it did, and what was ruled out. A terse commit makes a
poorer history, which is the intended pressure.

## Hard-won rules

### THE FORMAT IS THE ASSET, NOT THE INDIVIDUAL PIECE

"Broadside" is his word and it is better than "thinking tool": historically exact — a
single sheet, printed one side, argument plus information, meant to be posted and
passed on — and nobody else in this space is using it.

Two consequences. **A reader who finds five forms a different impression than one who
finds an orphan page**, so every broadside should link to an index. And **a series
title is registrable where a single work's title is not** — so "CHAMY·XYZ BROADSIDES"
can be an asset that no individual piece can be.

### ONE FILE, ALWAYS — AND THIS REPO DOES NOT YET MEET IT

The rule, from `radi/CLAUDE.md`: everything inlined, no build step, no dependencies,
opens from a folder on a desktop, still opens in 2046. For a resource meant to be
passed on that is the point rather than a constraint, and it is the most indie-web
idea in the catalogue.

**`index.html` currently breaks it.** It reaches for three sibling files:

    url('fonts/FFont-Bold.woff2')  ·  -Hairline  ·  -Regular

Send somebody the HTML alone and the typography silently falls back — the page looks
merely *plain*, so nobody reports it, they just think less of it. That is the exact
failure the one-file rule exists to prevent.

**Fix: inline the three faces as `data:` URIs** inside the `@font-face` blocks. Adds
roughly 200 KB and removes the only real dependency. The Google Fonts link may stay;
it is the documented exception.

### THE FONT IS ALSO A LICENSING QUESTION, NOT ONLY A PACKAGING ONE

`FFont` is the same family sitting in the **public** repo `2urn/f`. If it is a
licensed commercial typeface, it is now exposed in two places, and inlining it here
puts a redistributable copy inside a document meant to be passed on. **Settle what
`FFont` actually is before inlining anything** — see triage#1.
