# 27th Marketing intro: skills, prompts, storyboard

How the intro film for 27thmarketing.com/Services was made, so it can be repeated for the next one.

```
skills/lemo-opuscar/   the film skill (it downloads the Lemo-Opuscar style library when it first runs)
prompts/               the brief template and the follow-up prompts, in the order they were used
storyboard/            TREATMENT.md (structure, shot list, cue map) and the storyboard sheets
```

## Install

You need Claude Code (or any Claude client that loads skills from `~/.claude/skills/`), plus these on your computer:
git, Node.js, ffmpeg and Python 3.11 or newer. The skill reports anything missing and does not install system software itself.

1. Copy the skill into your skills folder:
   ```
   mkdir -p ~/.claude/skills
   cp -r skills/lemo-opuscar ~/.claude/skills/
   ```
2. Start a new Claude session so the skill is picked up.
3. Ask for a film (see below). On first use the skill runs `scripts/setup.sh`, which clones the style library from
   https://github.com/lemomo-ai/lemo-opuscar into `~/lemo-opuscar`, then installs the core tools (a few minutes the first time).
   You can also run it yourself: `sh ~/.claude/skills/lemo-opuscar/scripts/setup.sh` and `sh ... deps`.

Rendering a 4K film is heavy. Expect it to take a long while on a small machine, and keep a few GB of disk free.

## How to write a prompt like the one used here

The intro came out of four short messages, in this order. The templates are in `prompts/`.

1. **The brief.** Say what the film is for and where it will live, give the brand links (site, socials), and attach the logo.
   Include the job it must do (here: open the Services page, readable on mute).
2. **Answer the one round of questions.** The skill asks a few things. The answers used here: general audience (not one niche),
   text only with no voiceover, soft music, English only, about 35 to 40 seconds, 16:9.
3. **Set the look in plain words and give one reference.** "Minimal, smooth, cinematic, 4K, like an Apple motion graphic", plus a link
   to a video that has the feel you want. A reference is for feel, not for copying shots.
4. **Ask for the storyboard first.** Approve the structure before anything renders. Then give the green light with a clear bar,
   for example: "upscale the logo where quality is low, improvise the numbers, keep the badges, go all out".

Tips that made the result better: name the things you want kept, say which facts are placeholders so they can be swapped later,
and ask for deliverables by name (4K master, 1080p web file, poster, embed snippet).
