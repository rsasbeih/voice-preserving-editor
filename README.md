# voice-preserving-editor

A Claude skill that edits your writing for typos, grammar, and filler while protecting your voice instead of flattening it.

Most editing tools make writing *more correct* by making it *less yours*. They strip hedges, impose contractions, smooth the rhythm into something even and clinical, and reach for words nobody says out loud. This skill fixes the mechanical problems and leaves the rest alone.

## What it does

- Fixes typos, spelling, doubled words, agreement errors, tense slips, and sentences missing a connective.
- Strips transcription junk from voice memos: "um," "uh," false starts, self-corrections, and mis-transcriptions.
- Gives circular dictation a spine so it moves forward, using your words rather than rephrasing into its own.
- Removes AI tells: imported vocabulary, constructed "it's not X, it's Y" aphorisms, and over-polish.

## What it deliberately leaves alone

- Hedges and softeners ("kind of," "honestly," "I mean," "maybe"). Removing them makes you sound like you're handing down rulings.
- Contractions, in either direction. If you wrote "they are," it stays "they are."
- Repetition that builds, rhetorical question runs, long comma-chained sentences, pop-culture asides, ALL-CAPS emphasis, and sentences that start with And or But.
- Strong opinions stated as opinions. It flags the ones likely to draw pushback rather than softening them.

If a draft already sounds like you, it makes very few changes, or none.

## Editing modes

The skill picks a mode and tells you which one it used:

| Mode | For | Expect |
| --- | --- | --- |
| **Light pass** (default) | Drafts you already wrote and like | Typos and glue only |
| **Heavy pass** | Rambly voice memos and dictated transcripts | Cut hard, restructure, roughly half the length |
| **Structural rework** | "This isn't working" | A plain-terms diagnosis first, then the rewrite |

## Flags rather than silent fixes

Some things it surfaces and lets you decide on, instead of overwriting: suspected factual errors, internal contradictions (it quotes both spots), wrong-word-by-meaning slips like oven/stove, shaky technical claims, product name spellings, and paraphrases of real people.

## Install

**As a personal skill.** Clone into your Claude skills directory so the folder name matches the skill name:

```bash
git clone https://github.com/rsasbeih/voice-preserving-editor.git ~/.claude/skills/voice-preserving-editor
```

On Windows, that target is `%USERPROFILE%\.claude\skills\voice-preserving-editor`.

**As a bundle.** `voice-preserving-editor.skill` is a zipped copy of the same `SKILL.md`, for uploading to clients that take packaged skills. It's an ordinary ZIP archive with a different extension, so if you want to look inside it, copy it and rename the copy to `.zip`.

Either way, `SKILL.md` and its YAML frontmatter are the skill. This README is just for people reading the repo.

## Triggering it

It fires on its own when you ask Claude to edit, clean up, tighten, polish, fix, or "de-AI" something you wrote, when you hand over a voice-memo transcript to turn into a post, when you ask it to continue a draft in your voice, or when you ask what's wrong with a piece. "Edit this" is enough. You don't have to name it.

## Companion skill

It's built to run alongside `humanizer` (based on Wikipedia's "Signs of AI writing"), which it consults on every pass to catch tells and then check it didn't introduce new ones in its own edits.

## License

MIT. See [LICENSE](LICENSE).

## The rule underneath all of it

When choosing between "more polished" and "more like them," choose them every time. A withheld edit is a small loss. An edit that sands off your voice is a real one.

You make the final call on everything.
