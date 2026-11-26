# LOL AD Coach | Scenario-based AI coaching skill

[繁體中文](DESIGN-NOTES.md) | **English** | [日本語](DESIGN-NOTES.ja.md)

> Project type: an AI assistant workflow and prompt skill, not a standalone game app, a Riot API service, or a trained game AI.

## What does it do?
It organizes the needs of League of Legends AD players during draft, laning, teamfights, and review into scenario-specific response rules. Advice should fit the player's time constraints and familiar champion pool instead of producing a generic guide each time.

## Four modes
1. **Rapid draft:** Lead with an actionable pick, then briefly give the reason, early-game conditions, and an alternative when necessary. Do not spend the countdown looking up a long list of data.
2. **In-game:** Once the champion is locked in, advise on wave management, trading conditions, key abilities, and when to enter teamfights. Do not ask the player to switch champions.
3. **Review:** Use player-provided screenshots, footage, or timestamps to separate facts, inferences, and repeatable next actions. Focus on a few high-impact issues.
4. **Research:** If current patch information or statistics are needed, check Riot's patch notes and sources such as DeepLOL and OP.GG. State the patch, date, and data limitations.

## Technologies and skills
- **Custom `lol-ad-coach` Skill:** Markdown and YAML front matter define when to use it, modes, response formats, and evidence rules.
- **Prompt and workflow design:** Separate fast draft advice from deep research. Adjust for locked picks, champion familiarity, and uncertainty.
- **Multimodal AI:** Interpret images or footage provided by the user where the environment supports it. This is not a claim to have developed a separate vision model.
- **Web research:** Look up public patch and statistics data as needed. DeepLOL and OP.GG are reference sources, not completed API integrations.
- **Personalization:** The original environment has player preference data; public documentation contains no personal accounts, match histories, or private information.

## My role and the AI’s role
I described player needs, familiar champions, improvement goals, and response preferences, and pointed out recognition failures or unsuitable advice during actual conversations. AI organized those requirements into skill rules and provided conversational suggestions. It demonstrates scenario analysis, prompt design, and iteration based on user feedback, not independent development of a complete coaching application.

## Example scenarios
- Draft countdown: provide both bottom-lane pairings and ask for one priority pick and an early-game action.
- Champion locked in: ask when to trade and which enemy ability needs to be used first before stepping forward.
- Postgame: share actual footage and request “facts → assessment → next action.”

Example input:

> I have already locked in Jhin. The enemy lane is Kai'Sa with a support who can initiate. Give me the laning principles through level three first; do not suggest a different champion or guess abilities or positions you cannot see.

## Status and limitations
The `lol-ad-coach` rules have been confirmed in the conversational environment. Before documentation work, the original local project only had Git initialization and an ignore configuration. The public version exports SKILL.md and a generic player profile template, but it is not an executable application.

It does not read game memory live, control characters, or automate gameplay. Guidance can be outdated or affected by visual recognition errors, and statistics do not guarantee wins. No systematic outcomes assessment has been done or improvement in rank or win rate claimed.

The public version includes a de-identified `SKILL.md` and generic player profile template. Installation depends on the AI platform. This is a workflow specification, not a finished product.
