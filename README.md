<p align="center">
  <a href="https://www.livinginmovie.com/en?utm_source=github&utm_medium=skills-repo&utm_campaign=skills">
    <img src="https://frame-flavor-cdn.b-cdn.net/github/cadabraai/20261111061243-banner.png" alt="Cadabra AI: Claude skills for AI films" width="100%">
  </a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/license-MIT-green" alt="MIT license">
  <img src="https://img.shields.io/badge/works%20in-Claude%20%7C%20Claude%20Code%20%7C%20ChatGPT-blue" alt="Works in Claude, Claude Code and ChatGPT">
  <img src="https://img.shields.io/badge/video-Seedance%202.5-purple" alt="Seedance 2.5">
</p>

# Cadabra AI Skills

> **Runs on Cadabra AI.** The story and the prompts are free; images and video
> cost credits, and every price is shown before anything runs.

Skills that teach Claude to direct films like a production team: the story, the
characters, the look, the acting, the shots and the edit. You write one
sentence; Claude does the directing.

**Two ways to use them:**

- **Prompt mode, free, no account** (Animated Short). The skill writes the
  story, designs the character and writes every prompt in full, ready to copy
  into any engine. Cinematic Ad and Genie Edit need the connector.
- **Connected to Cadabra AI.** The same skill makes the pictures and the video
  right inside the chat, through the Cadabra AI connector. Images and video
  cost credits, and every price is shown before anything runs. A result that
  does not arrive is refunded.

---

## The skills

| Skill | You say | You get |
|---|---|---|
| [**Animated Short**](skills/cadabra-animated-short) | "Make an animated Short about..." | Your own 30-second animated Short. Your story, an original character with a locked shape, the look you pick (3D, clay, hand-drawn, watercolour, paper, felt, neon, ink), a hero picture, a character sheet and one Seedance 2.5 take directed beat by beat, with an end state for every beat |
| [**Cinematic Ad**](skills/cadabra-cinematic-ad) | "Make an ad for my business" | A 30-second cinematic commercial for any business, built from your real photos and facts: the owner as a legend, one hard stop, the reveal of the real shop, the offer |
| [**Genie Edit**](skills/cadabra-genie-edit) | "Edit this into a reel" | Your clips, a long recording or a finished film, cut into a finished film: captions, music, titles, end card |

The creation skills hand their files to Genie Edit. Editing is always its own
step.

## What makes them different

- **Story first.** No picture is made before the story is locked in three lines.
- **Every user gets a different film.** The skills build from your idea, never
  from a template film.
- **Direction an engine understands.** Acting tasks (want, why, obstacle,
  tactic), a visible end state for every beat, the hero picture as the first
  frame, a shape lock against things in the frame, one craft line and one
  motion line per look.
- **Money in the open.** A budget card before the first paid step, a quote
  before every step, a receipt after it.

## Install

**Claude (claude.ai or the desktop app)**
1. Download the skill folder as a ZIP (or use the
   [Animated Short ZIP](https://frame-flavor-cdn.b-cdn.net/guides/imaginary-friends/20261111062737-cadabra-animated-short.zip)).
2. Open **Settings**, then **Skills**, and upload the ZIP.

**Claude Code**, as a plugin (the skills and the Cadabra AI connector in one step):
```bash
claude plugin marketplace add CadabraAI/skills
```
```bash
claude plugin install cadabra@cadabra-ai
```
or the skills alone:
```bash
npx skills add CadabraAI/skills
```

**ChatGPT**
Put the skill's `SKILL.md` and its `references` files in a Project as files,
and install the Cadabra AI plugin from the Plugins page.

## Connect Cadabra AI (optional, to make the films in the chat)

In Claude, open **Customize**, then **Connectors**, then **Add custom
connector**, and paste:

```
https://mcp.livinginmovie.com/mcp
```

Sign in and click **Allow**. The full walkthrough:
[Connect Cadabra to Claude](https://www.livinginmovie.com/en/guides/cadabra-mcp?utm_source=github&utm_medium=skills-repo&utm_campaign=skills).

## Made with this method

<p align="center">
  <a href="https://youtu.be/7y06Z1M2-fI">
    <img src="https://frame-flavor-cdn.b-cdn.net/guides/imaginary-friends/20261109-cover.jpg" alt="Imaginary Friends, a 3D animated short made in one chat" width="70%">
  </a>
  <br>
  <i>Imaginary Friends: a 3D animated short made in one chat with Claude, with the method these skills package.
  Every prompt is open in the
  <a href="https://www.livinginmovie.com/en/guides/imaginary-friends?utm_source=github&utm_medium=skills-repo&utm_campaign=skills">free guide</a>.</i>
</p>

## License

MIT. Use the skills, change them, build on them.
