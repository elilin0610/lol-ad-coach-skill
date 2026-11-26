# LOL AD Coach Skill

[繁體中文](README.md) | **English** | [日本語](README.ja.md)

An **AI conversation coaching skill** designed for situations faced by League of Legends AD players. It is not a standalone app or a game add-on, and it does not integrate the Riot API or use a model trained for this project.

## Contents
- [SKILL.md](SKILL.md): Mode selection and response rules for the four modes.
- [Player profile template](references/player-profile.md): A generic template with no personal account data.
- [Design notes](DESIGN-NOTES.en.md): Requirements, division of work with AI, and limitations.

## Four modes
1. **Rapid draft:** Give an actionable pick first, followed by a short reason and an early-game action.
2. **In-game advice:** After the champion is locked in, cover wave management, ability windows, and teamfights rather than suggesting a different champion.
3. **Review:** Separate observable facts, inferences, and next actions, focusing on a few high-impact issues.
4. **Research:** When patch-specific data is needed, consult official patch notes and statistics, and provide sources, dates, and limitations.

## How to try it
Start by reading SKILL.md and use it as operating guidance for an AI assistant you have authorized. In an environment that supports SKILL.md, follow that platform’s official process for adding it to the skills directory, preserving the relative location of references. Installation, image/video support, and browsing vary by platform. This repository does not connect accounts or grant tool access.

Adapt the generic player template with preferences you are willing to share, then try a question such as:

> I have locked in Jhin. Start with the first three waves and when to trade. Do not guess unseen cooldowns or the enemy jungler’s position.

## Technologies and capabilities
Markdown, YAML front matter, prompt and scenario routing, separation of evidence from inference, and concise response constraints. Image analysis and web research depend on the AI platform. DeepLOL and OP.GG are possible public sources, not built-in APIs.

## Development approach: incremental learning with Socratic Tutor
I used the **Socratic Tutor** Skill during development to learn and discuss the project one step at a time instead of treating it as a one-shot generated result.

Socratic Tutor is a learning aid that guides thinking through questions. It is distinct from this project’s `lol-ad-coach` gameplay skill. This records my development and learning process; it does not claim that I built Socratic Tutor or that it includes a code generator, game engine, or Riot API integration.

There is no public step-by-step lesson record or assessment. This account is not a claim that I can independently build complete software.

## My role and the AI’s role
I provided gameplay scenarios, response preferences, and feedback from use; AI helped organize them into a reusable specification. The project demonstrates requirements analysis and AI workflow design rather than independent end-to-end software development.

## Limitations and public scope
The public version removes private player identities and account history and uses a generic template. It includes only the user-authored skill and project documentation, not platform-internal rules or third-party code frameworks. Its effect on win rate or rank has not been quantified; advice may be affected by patch changes or recognition errors. It does not automate gameplay or guarantee rank gains.
