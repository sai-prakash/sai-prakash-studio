# Sai Prakash
Staff Design Engineer, VP. JPMorgan Chase. LLM products, agents, evals.

> Built for people. Read by agents. Proven in production.

I'm Sai Prakash. I ship LLM products, build agents and the tooling around them, and measure whether they work. More than 12 years between design and code, most recently in production AI at JPMorgan Chase.

## Facts
- **Now:** VP, Staff Design Engineer on the Manhattan Design System at JPMorgan Chase
- **Builds:** LLM products · agents and MCP tooling · evaluation harnesses · accessible design systems agents can use
- **Before:** Senior UX Engineer at JPMorgan Chase · 11 years at SAP
- **Looking for:** Staff Design Engineer (UX Engineer, Design Technologist) · Applied AI Engineer
- **Can start:** 3 months after an offer · EU Blue Card eligible for Germany

## Proof
- **83%** less time on a liquidity task. 218 minutes became 37. (Liquidity Co-Pilot · shipped)
- **78%** less time per document. Now used in the commercial bank to create and verify golden data. (PromptForge · in production)
- **400+** opens a month. I own its UX and design research. (AI Assist Figma plugin)

## What I build
- **AI products in production:** Liquidity Co-Pilot (Shipped), PromptForge (In production)
- **Agents and AI tooling:** Design-system code agent (In build), LLM SDK, playground, API (Shipped), MCP audit and 10-tool spec (Done), This site's Studio (Live demo)
- **Evaluation:** Five-tier eval harness (Ready on web), Design-system linter (Hackathon win), Studio checks (Live demo)
- **Design systems for agents:** Layered specs (Reference build), This site's design system (Live), Accessibility tour (Live)

## Case files

### Liquidity Co-Pilot. A 218-minute task now takes 37.
Area: AI product. Status: Shipped.
- **Problem:** A liquidity task took about 218 minutes of manual work.
- **Move:** Liquidity Co-Pilot, an AI assistant for that work.
- **Result:** About 37 minutes, an 83% cut.
- **My part:** Built and shipped it.
- **Walkthrough:** on a call (How it works, end to end; How the 218 and the 37 were measured; The screens).

### PromptForge. Ninety minutes per document became twenty. Then it became a product.
Area: AI product. Status: In production.
- **Problem:** Each document took about 90 minutes of manual extraction and annotation.
- **Move:** PromptForge, an LLM platform for prompt engineering and document annotation.
- **Result:** About 20 minutes per document, a 78% cut. It's now a product the commercial bank uses to create and verify golden data.
- **My part:** Built and shipped it.
- **Walkthrough:** on a call (The pipeline and the models behind it; How golden data gets verified; From internal tool to product).

### Design-system code agent. Let the agent build only with parts the design system owns.
Area: Agent. Status: In build.
- **Problem:** General code generators ignore the design system, so their screens get rebuilt by hand.
- **Move:** An in-browser agent that builds screens only from the design system's real React components, with checks before anything is shown.
- **Status:** Single-screen and multi-screen generation work. The goal is React, iOS and Android for 5,000+ internal users.
- **My part:** Architecture, multi-screen generation and the data corpus. I build it hands-on.
- **Try it:** The Studio on this page is a small, public version of the idea, built on this site's own design system.
- **Deep cut:** encrypted on the page (Architecture in four parts; Why early output looked generic; The data behind it; Who built what). Key from Sai.

### Eval harness and linter. Measure the agent's output, not the demo.
Area: Evaluation. Status: Ready on web.
- **Problem:** Teams judge AI coding tools by demos. Few measure whether the output follows the design system.
- **Move:** A five-tier evaluation harness that scores agent-generated code. It's ready on web; Android and iOS are in progress.
- **Also:** A design-system linter that won a hackathon. Teams asked for it after the first demos.
- **Next:** ds-bench-de, a public benchmark of how well agents use the public design systems of German companies, such as SAP UI5, Siemens iX and Telekom Scale. The method publishes with the scores.
- **My part:** Concept, scoring method and harness.
- **Deep cut:** encrypted on the page (Five tiers, one harness; Where the test data comes from; The linter, from hackathon to leadership). Key from Sai.

### Layered specs. Give the agent twelve kilobytes first. Load the rest only when the task needs it.
Area: Design systems for agents. Status: Reference build.
- **Problem:** A full component spec is too big to send with every request. A thin one leaves the agent guessing.
- **Move:** Split each pattern's spec into layers. An index finds the pattern, a core layer under 12 KB covers the common case, and the full spec, tokens and a visual contact sheet load on demand.
- **Proof:** The Filter pattern as reference: 22 edge cases, 52 token bindings, passing eval suites.
- **Cost:** More files that have to agree with each other.
- **My part:** The layered architecture and the Filter reference implementation.
- **Deep cut:** encrypted on the page (The five files; How success is measured; How I took it to leadership). Key from Sai.

### LLM SDK, plugin, MCP. Give designers the model directly, without a ticket to engineering.
Area: AI tooling. Status: Shipped.
- **Problem:** Designers who wanted to try LLMs had to wait for engineering.
- **Move:** An SDK, a playground and an API that put the firm's internal models in designers' hands. A Figma plugin and MCP servers sit on top.
- **Result:** Designers try models on their own. The AI Assist Figma plugin reached 400+ opens a month.
- **My part:** The SDK, playground and API server, the plugin's UX and design research, and the MCP audit and spec.
- **Deep cut:** encrypted on the page (What shipped first; The Figma plugin; Getting models into Figma safely; MCP). Key from Sai.

## Design system
Sai Prakash Studio v1.2: 12 color tokens, an eight-step type scale in rem, a spacing scale of 4, 8, 12, 16, 24, 32, 48, 64, 96, 128 px, and 19 components. Full spec in design-system.json and DESIGN.md next to this file.
- **Section:** One idea per section. The label names it, the title says it.
- **Heading:** Headings sit inside a Section and never skip a level.
- **Text:** Short paragraphs, one idea each.
- **Label:** Labels are mono, upper case, five words at most.
- **Stack:** Stack things that are read top to bottom.
- **Row:** Put actions or chips that belong together in one row.
- **Grid:** A grid holds items of equal weight. It stacks on phones.
- **Card:** A card sets one thing apart. Not everything is a card.
- **Stat:** A big number always says what it counts.
- **Button:** One primary action per section. The text says what happens.
- **Chip:** A chip states a status in words, never by color alone.
- **Sutra:** The one-line rule. Fourteen words at most.
- **Quote:** Quote a person, with their role.
- **List:** Lists hold two to eight parallel items.
- **Steps:** Steps show a sequence. Mark the step that matters.
- **Bars:** Bars share one scale that starts at zero.
- **Strings:** The signature headline. Up to three lines of 24 characters.
- **Field:** Every field has a visible label.
- **Divider:** The double danda ends a section, the way it ends a verse.

## Studio
An agent turns a brief into a screen built only from these components. The page compiles the JSON as it streams and grades it with nine checks, then sends failures back to the agent once.
- Valid JSON
- Only system components
- No raw styling or unknown props
- Required content present
- One primary action per section
- Headings in order (WCAG 1.3.1)
- Every field has a label (WCAG 3.3.2)
- Copy follows the voice
- Numbers are real

## Accessibility
- **Works without a mouse:** Every control can be reached and used with a keyboard, in reading order. (WCAG 2.1.1 · 2.4.3)
- **Skip link and landmarks:** The first Tab reaches “Skip to content”. Header, navigation, main and footer are marked up as such. (WCAG 2.4.1)
- **Focus you can always see:** A clear ring on every control, never hidden under the sticky header. (WCAG 2.4.7 · 2.4.11)
- **Contrast, measured live:** Every text color pair is at least 4.5:1. The colophon measures it in your browser. (WCAG 1.4.3)
- **Never color alone:** Statuses and check results say their word, so grayscale loses nothing. (WCAG 1.4.1)
- **Text that grows:** Type is set in rem, and the layout reflows to one column instead of scrolling sideways. (WCAG 1.4.4 · 1.4.10)
- **No dragging required:** The seam moves with a tap or the arrow keys, not only by dragging. (WCAG 2.5.7)
- **Motion on your terms:** If you ask for reduced motion, nothing moves on its own. (WCAG 2.3.3)
- **Names, roles and labels:** Every control has a name, every field a label, every toggle a state. The colophon counts any that don't. (WCAG 4.1.2 · 3.3.2)
- **Your settings respected:** High-contrast and forced-color modes get stronger lines and system colors. (prefers-contrast · forced-colors)

## Path
- **SAP · 11 years:** UI Developer → Lead Product Designer → Innovation Architect. Worked on SAP's living style guide. Led design for mobile experience and Business Objects prototyping.
- **JPMorgan Chase · Corporate & Investment Bank:** Senior UX Engineer. Built a Figma-to-SALT pipeline that turns design files into design-system code.
- **JPMorgan Chase · Consumer & Community Banking · 2026:** VP, Staff Design Engineer. Making the Manhattan Design System AI-native at the point where design turns into code. Measured by design-to-code cycle time.

## How I multiply
- Gave designers direct model access with an SDK, a playground and an API.
- Took a hackathon win to design leadership.
- Explained the agent docs pipeline to design, product and tech leads as three decisions.
- Handed the Figma plugin to engineering and kept owning its UX research.

## Lab
- **Design System Search** (Live, EmbeddingGemma 2): 6/7 hand-picked queries top-1 over 19 components. https://ui-screenshot-search.vercel.app
- **Evidence Finder** (Live, EmbeddingGemma 2): 5/5 claims top-1 over 3 pages. https://hitl-evidence-finder.vercel.app
- **Agent UI Check** (Live, EmbeddingGemma 2): 11/11 planted defects caught. https://agent-ui-eval.vercel.app
- **UI Critic** (Prototype, SmolVLM 256M): vision model proposes defects, code verifies them. demos/ui-critic.html on this site.

- **Halo** (Side project): A command-line coding agent, plus a 3D office where tasks are split across a team of Halo agents.
- **Switchyard** (Prototype): One interface to run many Claude Code sessions as a team of agents.
- **copilot-coach** (Tool): Reads GitHub Copilot chat history across sessions and coaches better use. Two-stage cost design, stable anti-pattern IDs, a golden test set.
- **YaadKaro** (Live): Finds the Bollywood film or song you only half remember. https://yaadkaro.vercel.app
- **entropy-RLAF · agentic-design-thinking** (Open source): Public repositories on GitHub. https://github.com/sai-prakash/

## Notes

### Your design system has a second reader
October 2026 · 5 min read

AI agents now read the docs people wrote for each other. Here's what changes when you write for both.

For years a design system had one reader: a designer or engineer who could fill the gaps with judgment. Read “use the danger button sparingly” and you know what sparingly means. An AI agent doesn't. It reads the same page, guesses, and ships the guess.

That's the shift I work on. The docs aren't only documentation any more. They're an interface, and the agent is a user with no common sense, perfect recall of whatever you put in its context, and no recall at all of what you left out.

#### Write the rule, then the reasons

Guidelines written for people bury the rule inside the reasoning. Agents need the rule first, stated so it can be checked: one primary action per dialog; destructive actions use the danger variant; focus starts on the safe action. The reasoning still matters to the people who maintain the rule. It just goes second.

#### Budget the context

The next problem is size. A complete spec for one component runs long, and sending all of it with every request spends the agent's attention on edge cases it doesn't need. So I split specs into layers: a small index to find the pattern, a core layer under 12 KB for the common case, and the full spec, tokens and visual references loaded only when the task needs them. For the Filter pattern that kept 22 edge cases and 52 token bindings out of the way until they mattered.

#### Check that the agent listened

None of this counts until you measure it. Writing for agents without testing the output is writing for no one. The goal is a check behind every rule, and the scores show which rules the agent ignores. Usually that means the rule was written badly.

> If an agent keeps breaking a rule, read the rule again before you blame the agent.

### Measure the output, not the demo
October 2026 · 4 min read

AI coding tools win the room with demos. Here's what I measure instead.

Every AI coding tool demos well. You type a prompt, a screen appears, the room is impressed. The trouble starts a week later, when an engineer rebuilds that screen because it ignored the design system, invented a component or skipped accessibility.

A demo answers “can it make something?” A team needs to know how often it makes the right thing. Those questions need different evidence.

#### Grade against real work

Toy prompts flatter the model. A useful test set looks like the work the team actually does, so the agent is graded on screens and code that resemble what ships.

#### Score in layers

One overall number hides where things go wrong. The harness I built at work scores generated code at five tiers. Each tier gets its own score, so a weak result points somewhere specific: the prompt, the docs or the model.

#### Measure what people feel

For products, the honest metric is often time. With PromptForge, a document that took about 90 minutes came down to about 20. Liquidity Co-Pilot took a 218-minute task to 37. Numbers like these are what stakeholders remember, and what keeps a tool funded.

> A demo shows what the model can do once. An evaluation shows what it does every time.

The Studio on this page is a small version of the same loop: an agent builds, nine checks grade, and a failed check goes back to the agent once.

### Two letters, one set
October 2026 · 3 min read

More than 2,000 years ago, Pāṇini named whole sets of sounds with two letters. Design tokens do the same thing.

Pāṇini's grammar describes Sanskrit in nearly 4,000 short rules. Before the rules come 14 lines of sounds, and each line ends in a marker that isn't a sound at all. It's an index.

Rule 1.1.71 explains the trick. Take a sound, add a later marker, and you've named every sound in between. The sound a plus the marker c gives aC, all the vowels. The sound ha plus the marker l gives haL, all the consonants. Two letters name a set, and the grammar uses these names throughout.

#### That's a token alias

Design systems rediscovered the idea. We name a set once, like color.danger or space.6, and refer to it everywhere. Change the set and every rule that uses the name follows. The grammar stays short because the names do the work.

#### Why it matters more with agents

Short, exact names make a rule cheap to state and easy to check. That matters more now that agents read our systems. Give an agent “use danger for destructive actions” and a token called danger, and it can't misread the intent. Give it a paragraph about tone, and it can.

> Pāṇini wrote for readers who memorised every rule. Agents are those readers now.

In 1967 Peter Ingerman suggested calling Backus–Naur form “Pāṇini–Backus form”, because Pāṇini's rules work in a similar way. You can try the 14 lines yourself in the Method section of this page.

## Method
Rule 1.1.71 of Pāṇini's grammar: a sound plus a later marker names every sound in between. Two letters name a set, like a token alias.
1. Name a set once, then refer to it everywhere.
2. State the rule in one line. Keep the reasoning one tap away.
3. Write it so people and agents read the same thing.
4. Test that the agent followed it, and publish the score.

## Looking for
- **Roles:** Staff Design Engineer (UX Engineer, Design Technologist) · Applied AI Engineer
- **Open to:** Germany and the wider EU, US, Canada, Singapore, Australia
- **Based in:** Bengaluru, India (UTC+5:30)
- **Can start:** 3 months after an offer
- **Work permit:** Germany: qualifies for the EU Blue Card
- **Education:** BCA, BIT Mesra (2012) · M.Tech in Software Engineering, BITS Pilani (2016)

## Contact
- **Email:** saiprak@gmail.com
- **LinkedIn:** https://www.linkedin.com/in/prakashsai/
- **GitHub:** https://github.com/sai-prakash/

## Guide rules
The guide on this page answers only from the text above, cites the section it used, and declines questions about pay, personal life or confidential employer details.
