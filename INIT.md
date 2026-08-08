# Initialization Protocol

I want you to set up this project folder as my personal executive assistant / second brain. You're going to do this in 3 phases. Complete each phase fully before moving to the next.

## Phase 1: Harness Detection & Setup

Identify the AI harness/IDE you are running in (e.g., Claude Code, Cursor, Gemini, Antigravity, etc.).

1. **If you are running in Claude Code:**
   - Rename `AGENTS.md` to `CLAUDE.md`.
   - Rename the `.agents/` directory to `.claude/`.
   - Ensure all future references in this setup point to `CLAUDE.md` and `.claude/`.

2. **If you are running in Cursor, Gemini, Antigravity, or other systems:**
   - Keep `AGENTS.md` and the `.agents/` directory as they are.

Once this is confirmed and executed, proceed to Phase 2.

## Phase 2: Ask me onboarding questions

Before filling in the context files, rules, and the main brain file (`AGENTS.md` or `CLAUDE.md`), interview me. Ask these questions one section at a time. Don't dump all questions at once -- go section by section and wait for my answers before moving on.

### Section 1: About You
- What's your name?
- What's your role/title? (e.g., CEO, freelancer, content creator, developer)
- What's your timezone?
- In one sentence, what do you do?
- What's your #1 priority -- the thing everything else should support?

### Section 2: Your Business / Work
- What's your company or business called? (or describe your work if you're not a business owner)
- What are your products, services, or revenue streams? (List each with a one-liner)
- Roughly how much revenue does each generate? (optional, but helps me prioritize)
- What tools do you use day-to-day? (ClickUp, Notion, Slack, Google Workspace, etc.)
- Do you have any MCP servers already connected? (If you don't know what this means, just say no)

### Section 3: Your Team
- Do you have a team? If yes, how many people?
- Who are the 2-3 key people I should know about? (name, role, when to loop them in)
- Where does your team communicate? (ClickUp, Slack, etc.)
- What's your biggest pain point with managing your team?

### Section 4: Priorities, Goals & Projects
- What are the 3-5 things you're most focused on right now?
- Are there any deadlines or time-sensitive items I should know about?
- Do you have quarterly goals or milestones you're tracking? (If yes, list them. If you don't do formal goals, that's fine -- your priorities above will work.)
- What active projects or workstreams are you managing right now? (These are specific initiatives, not ongoing responsibilities. E.g., "launching a new course", "hiring a VA", "redesigning the website")

### Section 5: Communication Preferences
- How do you like information presented? (bullet points, detailed paragraphs, etc.)
- Any writing pet peeves? (e.g., "never use emojis", "no em dashes", "keep it under 3 sentences")
- What tone do you want internally (casual, professional, etc.)?
- What tone do you want for external/public-facing content?

### Section 6: What Do You Want Help With?
- What are the recurring tasks that eat up your time? (List as many as you want)
- What would you hand off to an assistant first if you could?
- Are there any specific workflows you want to automate or templatize?

## Phase 3: Build out the files

Based on my answers, fill in all the files in this template:

### Context files
- **context/me.md** -- My profile based on Section 1 answers
- **context/work.md** -- My business/work details based on Section 2 answers
- **context/team.md** -- Team structure based on Section 3 answers (if I have a team; if solo, note that and clear the file)
- **context/current-priorities.md** -- Priorities from Section 4, dated today
- **context/goals.md** -- Quarterly goals and milestones from Section 4. If no formal goals, use top priorities as informal goals. Date it with the current quarter (e.g., "Q2 2026"). Include a note at the top: "Update this file at the start of each quarter."

### Projects
If I listed active projects in Section 4, create a folder for each inside `projects/` (create the `projects/` directory if it doesn't exist). Each project folder gets a brief `README.md` with:
- One-line description of the project
- Current status (active, planning, on hold)
- Key dates or deadlines mentioned

### Rule files in `<harness_dir>/rules/`
Create rule files based on my communication preferences (Section 5). Suggested files:
- **communication-style.md** -- Writing tone, formatting preferences, pet peeves
- Any other domain-specific rules that emerged from my answers.

Keep each rule file focused on ONE topic. Don't create more than 3-4 rule files to start.

### The Main Brain File (`AGENTS.md` or `CLAUDE.md`)
Update the main brain file in the root directory. Keep it UNDER 150 lines. It should contain:

1. **One-line identity** -- Who you are to me (e.g., "You are [Name]'s executive assistant.")
2. **Top priority** -- The #1 thing everything supports
3. **Context imports** -- Use `@context/me.md`, `@context/team.md`, `@context/goals.md`, etc. to reference files instead of repeating their content
4. **Tool integrations** -- What tools are connected
5. **Skills directory** -- Point to `<harness_dir>/skills/` and explain how skills work
6. **Decision log** -- Point to `decisions/log.md` and explain append-only convention
7. **Memory** -- Add a section explaining how memory works:
   - "Your assistant maintains a persistent memory across conversations. As you work, it automatically saves important patterns, preferences, and learnings. You don't need to configure this -- it works out of the box."
   - "If you want your assistant to remember something specific, just say 'remember that I always want X' and it will save it."
   - "Memory + context files + decision log = your assistant gets smarter over time without you re-explaining things."
8. **Keeping context current** -- Add a brief maintenance section:
   - Update `context/current-priorities.md` when your focus shifts
   - Update `context/goals.md` at the start of each quarter
   - Log important decisions in `decisions/log.md`
   - Add reference files as needed
   - Build skills when you notice you're repeating the same request
9. **Projects** -- Point to `projects/` and explain that active workstreams live there
10. **Templates** -- Point to `templates/`
11. **References** -- Point to `references/`
12. **Archives rule** -- Don't delete, archive

Do NOT put communication style rules in the main brain file -- those go in `<harness_dir>/rules/communication-style.md`.
Do NOT repeat context from the context files -- just import them with @.

### Skills directory
Make sure the main brain file mentions that skills live in `<harness_dir>/skills/` and explains the pattern:
- Each skill gets a folder/file
- Skills are built organically as recurring workflows emerge
- Include a note about my answers from Section 6 (what I want help with) as a "Skills to Build" backlog in the main brain file or a separate file.

## Final Step

After everything is created:
1. Show me a tree view of every file and folder you modified/created
2. Show me a brief summary of what's in each file (one line per file)
3. List the "Skills to Build" backlog based on my Section 6 answers -- these are the workflows we'll turn into skills over time
4. Show me this maintenance cheat sheet:

**Keeping Your Assistant Sharp**
- **Weekly:** Nothing required. Auto-memory handles daily learnings for you.
- **Monthly:** Glance at `context/current-priorities.md`. If your focus has shifted, update it.
- **Quarterly:** Update `context/goals.md` with new goals and milestones.
- **As needed:** Log decisions in `decisions/log.md`. Add reference files. Build new skills.
- **Pro tip:** If you want your assistant to remember something permanently, just tell it: "Remember that I always prefer X." It will save it across all future conversations.

5. Ask me if I want to build any of those skills right now.

## Important Rules for You (The AI Agent)

- Do NOT create any skills yet.
- Keep the main brain file UNDER 150 lines.
- Use @ imports (e.g., @context/me.md) in the main brain file instead of repeating information.
- One rule file = one topic. Max 3-4 rule files to start.
- Ask onboarding questions ONE SECTION AT A TIME. Wait for my response before asking the next section.
- If I say "skip" or "I'll fill that in later" for any section, leave the files blank and move on.
