# Every new feature in the rebuilt Claude Code app

The full list from my reel. In October 2026 Anthropic rebuilt the Code tab of the Claude desktop app (Claude Desktop v2.42304.0, 15 Oct 2026).

Each item says what it is, how to open it, and the catch. Every one is checked against Anthropic's own docs or changelog, linked at the bottom. 🇵🇱 Po polsku: [PL.md](PL.md)

---

## The 3 from the reel

### 1. Side chats: ask a question without derailing the task
- **What:** a chat beside the session that can read everything in the main thread up to that point. Nothing you ask there lands back in the main conversation.
- **Open:** `Cmd+;` on macOS, `Ctrl+;` on Windows, or type `/btw` in the prompt box. Each side chat gets its own tab.
- **Catch:** side chats are **not saved**. Close the app and they're gone, so copy anything useful.

### 2. Projects: one coordinator chat that runs a small team
- **What:** one ongoing conversation that starts a thread for each task, keeps track of all of them, and gets their reports back. Threads share one project memory, and cloud threads keep going after you close your laptop.
- **Who:** public beta on Pro and Max. Not on Team or Enterprise yet.
- **Catch:** projects burn usage faster. There's a hard cap of 200 new threads per day.
- **Local version: nested sessions.** In local and SSH sessions, Claude can start a task in a separate session that sits under the original one in the sidebar and reports back to it. In **Settings › Claude Code** you choose what happens when you ask for something unrelated.

### 3. `/skill-doctor`: find the skills eating your context
- **What:** every skill you install adds to your context **on every turn, whether or not Claude ever uses it**. `/skill-doctor` shows what each skill costs and how often it actually gets used, so you can remove the dead weight.
- **Open:** type `/skill-doctor`. Needs Claude Code 2.1.252 or newer; the report opens in `/plugin` › Stats.
- One creator (Ben AI) cut about 20,000 tokens this way. That's his own test, not an official number.

---

## Everything else that's new

### The session rail (cards beside the chat)
A rail on the right of the conversation, with cards for environment, context, connectors, outputs, changes, servers and background tasks. Right-click a card's header to choose which cards show.
- **Context card:** how full the context is and what's using it.
- **Environment card:** local or cloud, plus the **Remote Control** switch to carry on the session from your phone.

### The plan box
While Claude works, a box at the end of the conversation shows its plan and ticks off the steps. When the turn ends it can show a short recap with buttons for the next step. Local and SSH sessions only.

### Sections
Group your sessions in the sidebar. Custom groups are now called sections, and you can also group by environment.

### Saved environments
Save a folder, SSH host, cloud environment or Remote Control machine, then pick it when you start a session.

### Sessions that talk to each other
Claude can list your other Code tab sessions, read what each has been doing, and send messages between them. Ask in plain language, for example "tell the payments session the schema changed". It sees your 20 most recently active sessions.

### Split view
Two sessions side by side. Hold `Option` (macOS) or `Alt` (Windows) and click a session, or right-click it › **Open in** › **Split view**. This one isn't new in October, but most people never found it.

### Slash commands worth knowing
- `/output-style`: switch how Claude answers, for example `/output-style concise`. The built-in styles are Proactive, Concise, Explanatory and Learning, and the desktop app can draft a custom style from a plain description.
- `/doctor`: a setup checkup for installation, settings, extensions and CLAUDE.md.
- `/doctor prompt-audit`: audits your CLAUDE.md files and skills for outdated or conflicting instructions. This is the one to run if your setup is a few months old.
- `/advisor`: a cheaper model consults a stronger one (Opus or Fable) at key moments. It's experimental and works on the Anthropic API only.

### Mods
Small TypeScript functions that change how Claude Code works: rewrite a prompt before it reaches the model, block or rewrite tool calls, redact secrets, or add your own panes and buttons. The built-in `/diff` is now a mod. **Catch:** mods run with the same access to your machine as Claude Code itself, so read any mod before you install it.

### Docs, Slides, Design, Dashboards, Motion
- **Docs, Slides and Design** are out of beta and available on every plan, including Free.
- **Dashboards** (beta, paid plans): click any number to see the query behind it. Each chart shows when its data was last refreshed.
- **Motion** (beta): animated videos made in code, with no video model and no AI-generated people. Type `/motion`. It's **Team and Enterprise only**.

---

## Should you move from Cowork to the Code tab?
That's Ben's take and mine too: new features land in the Code tab first, and it's not only for coders. Officially, Cowork and chat are merging into "one Claude", rolling out on Pro and Max.

## Sources (all official)
- Claude Desktop changelog: https://claude.com/docs/cowork/changelog
- Desktop docs (side chats, split view, environments, cross-session messages): https://code.claude.com/docs/en/desktop
- Projects: https://code.claude.com/docs/en/claude-projects · https://claude.com/blog/projects-redesigned
- Skills, `/skill-doctor`, `/doctor`: https://code.claude.com/docs/en/skills
- Commands and `/output-style`: https://code.claude.com/docs/en/commands
- `/advisor`: https://code.claude.com/docs/en/advisor
- Mods: https://claude.com/resources/articles/claude-code-mods
- Dashboards and Motion: https://claude.com/resources/articles/dashboards-and-motion
- Cowork is now Claude: https://claude.com/blog/cowork-is-now-claude

Inspired by Ben AI's walkthrough "Claude 2.0 is Insane": https://youtu.be/J5EbL1UaqG8

---
Made by Kris · [@aipractically](https://www.instagram.com/aipractically/) on Instagram · [@kris.aiwpraktyce](https://www.tiktok.com/@kris.aiwpraktyce) on TikTok
