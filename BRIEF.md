# Meet Your Chief of Staff — Build Brief

**Artifact:** Single-file HTML presentation, "Meet Your Chief of Staff," for Einstein Moving Company's Roundtable leadership rollout.
**Hosting:** Public-but-obscure GitHub Pages (new repo under `einsteinadmin/`), obfuscated URL pattern, `noindex/nofollow` meta + `robots.txt` disallow. Treat as internal-facing.
**Dual-mode delivery:** Same artifact serves (a) Cameron walking through it live with leadership, and (b) leaders re-opening it solo afterward to re-read.

---

## Audience

Mixed Roundtable, all consuming the same artifact:

- **Brian Herzig** — CTXH Regional Mgr + Culture Head. Non-technical.
- **Mike Vandenbroader** — DFWT Regional Mgr + Head of Ops. Semi-technical, already runs his own COS (Gerald).
- **Anne Bosse** — Director of Employee Experience. Non-technical.
- **Amanda Ware** — Director of Customer Experience. Non-technical.
- **Matisen Harper** — Director of IT. Deep technical, runs his own COS already.
- **Paul Morin** — CFO/COO. Non-technical. Just onboarded Clark on Windows.

Pitch the body copy to the **non-technical middle**. Put deeper technical detail behind collapsible "How it actually works under the hood" sections so Matisen + Paul can dig in without slowing Brian + Anne down.

---

## Voice

Cameron's voice. Direct, conversational, warm. Like a smart friend explaining tech to a peer, not a consultant pitching.

- **Analogies are the highest-leverage tool — use them liberally:**
  - File system = filing cabinet on your desk
  - MCPs = wires plugged into the apps you already use
  - Memory = what your COS remembers across coffee chats
  - Skills = saved playbooks the COS already knows by name
- Light humor when it lands.
- **Never use:** "I'm thrilled to..." / "fostering a culture of..." / "Great question!" / "Absolutely!" / em-dash-heavy AI cadence / "truly exemplified"
- **Default to** concise and human.

**Hard gate:** Read `Cameron Writing Style SKILL.md` before writing any copy. Run the 6-pattern AI-tell filter on every draft before declaring sections done.

---

## Design

Follow `einstein-frontend-design-SKILL.md`:

- **Color:** Einstein orange `#EF8B22` (Pantone 144C) as primary accent
- **Type:** Roboto (load explicitly from Google Fonts, don't rely on system fallback)
- **Layout:** Clean, conversion-focused, generous whitespace

Mirror the architecture patterns from the Q1 QGR packet (live at `qgr.einsteinmoving.com`):

- Sidebar TOC with section jumps (left side, sticky)
- Hamburger drawer below 980px (orange FAB bottom-right, scrim backdrop, Esc/scrim/link-click closes)
- Component cards in a responsive grid that stack cleanly on mobile
- Click-to-expand lightbox for any diagram (generic `.lightbox-trigger` handler)
- Mobile-first responsive — must QA clean at **360, 414, 768, 1024, 1440px**
- Hero block at top with one-line value prop
- Aggregate stat cards where they fit naturally (e.g. "4 COS agents live across Einstein leadership today")

---

## Naming — Leader Fills In Their Own

Each leader names their own COS as part of Phase 1.

- **Do not pre-fill names anywhere in the artifact.**
- Use placeholder format `"your COS (you'll name it in Phase 1)"` or a clearly-styled blank like `[Your COS Name]` wherever a leader's COS name would appear.
- Reference the existing named COSes (Albert, Gerald, Matisen's COS, Clark) **only** when describing the network or showing examples — never as a template for what theirs will be called.

---

## Required Sections (in order)

### 1. HERO — "Meet Your Chief of Staff"

- One-line definition: *an always-on AI teammate that lives on your laptop, knows your business context, and runs the busywork.*
- **Visual:** simple 4-layer stack diagram (You → Your COS → Your Tools → The Outside World). The COS is in the middle as the connector.
- Mention example COSes already live: Albert (Cameron), Gerald (Mike), Matisen's COS, Clark (Paul). Brian + Anne + Amanda are next.

### 2. THE THREE SURFACES — "Wait, isn't this just Claude?"

The single most common confusion. Resolve it upfront.

- Side-by-side comparison: **Claude Chat (claude.ai)** vs **Cowork (browser-controlling AI)** vs **Claude Code (the COS)**.
- Frame:
  - Chat = a brilliant intern with amnesia
  - Cowork = a remote assistant that can drive your browser
  - Claude Code = a teammate that lives on your machine, remembers everything, has every tool plugged in, and can actually act
- Why Code is the COS surface: file system access, persistent memory, MCP integrations, can run skills, can build things for you.

### 3. ANATOMY OF YOUR COS — "What lives on your laptop"

- **Visual:** file tree diagram showing the key pieces.
- `CLAUDE.md` = the instruction sheet your COS reads first every session (who you are, what matters, your preferences, current quarter, key people)
- `memory/` folder = sticky notes that survive across sessions (user preferences, feedback patterns, project context, references)
- `skills/` = saved playbooks the COS already knows
- `.claude/` = settings, hooks, permissions
- Your project folders = your actual working files (Einstein workspace at `~/Desktop/EMC Projects/`)
- **Collapsible technical detail:** how `settings.json` + hooks + permissions actually configure behavior

### 4. MEMORY — "How it remembers you"

The COS writes new memory automatically when it learns something durable. **Four types:**

- **User memory** — who you are, how you work
- **Feedback** — corrections + validated approaches (both directions)
- **Project** — active initiatives, deadlines, decisions
- **Reference** — where to look in external systems

- `MEMORY.md` = the index (one line per entry). Memory files = the detail.
- Show a real anonymized example from Albert's memory ("never wrap Monday updates in CDATA" — with the *why*) so they see the format and the reasoning style.
- Frame: this is why the COS gets sharper the longer you work with it.

### 5. SKILLS — "The shortcuts your COS already knows"

Skills = named playbooks. Type `/skillname` and the COS executes the whole workflow.

**Starter skills they'll use day-one (with one-line descriptions):**

- `/gm` — Good Morning briefing (calendar + Monday + notifications + day plan)
- `/wrap` — End-of-day wrap (velocity, praise queue, tomorrow prep)
- `/save` — Mid-session context handoff
- `/meeting-prep` — Standardized prep doc for any sync
- `/digest` — Post-meeting processing (transcript → pulses updated)
- `/grade-meeting` — Facilitation coaching

**Phase 2 skills they'll grow into:** `/retro`, `/scout`, `/consultants`, `/loop`, custom skills they build themselves.

Frame: skills are how your COS scales. Cameron has 40+ skills today. Every leader builds the set that fits their work.

### 6. MCPs & APIs — "The wires to your tools"

- **MCP** = Model Context Protocol = the standard way Claude Code plugs into outside apps.
- **Visual:** hub-and-spoke diagram with the COS in the middle and Monday, Slack, Google Drive, Google Calendar, Gmail, Dialpad, Samsara, ClearCo around it.
- **Plain-language frame:** *"When you ask your COS to post an update to a pulse, it doesn't open Monday in a browser — it sends the request directly through the Monday API in milliseconds."*

**What each integration unlocks** (one sentence each, framed by use case not capability):

- **Monday** → pulse triage, update posting, weekly velocity
- **Slack** → message reading, draft + send (with your approval), channel scanning
- **Drive** → file creation, sharing, search
- **Calendar** → meeting prep, scheduling conflicts, time-zone sanity
- **Gmail** → inbox triage, draft replies, search
- **Dialpad** → call grading, sales coaching
- **Samsara** → driver score visibility, warnings audit

**Collapsible:** how MCPs vs raw APIs work, when each is right.

### 7. THE NETWORK — "Your COS isn't alone"

- **4 COS agents live at Einstein today:** Albert (Cameron), Gerald (Mike), Matisen's COS, Clark (Paul). Brian / Anne / Amanda joining soon.
- **Shared Context Board** (Monday board `18407411332`) = the agent-to-agent comms layer. Public to all COSes.
- When Cameron's Albert needs something from Mike's Gerald, it posts to SCB. Gerald sees it next session, replies, both principals stay in the loop.
- Frame: this is how a fleet of COSes coordinates without humans manually relaying every handoff.
- **Visual:** simple network diagram with the 4 live COSes + SCB at center, plus 3 ghosted nodes for the upcoming leaders.
- **Public onboarding repo:** `github.com/einsteinadmin/ai-chief-of-staff` — every COS pulls from the same template, so improvements propagate.

### 8. YOUR ROLLOUT — "What the next few weeks look like"

- **Phase 1: Setup (week 1)** — Anthropic Org account, install Claude Code, pull the COS template, name your AI, first session. **CTA button** links to the Anthropic Org Setup Checklist (interactive 6-step tool — URL placeholder, see flag below).
- **Phase 2: Daily rhythm (week 2)** — Run `/gm` every morning, `/wrap` every Friday, `/meeting-prep` before syncs. Build the muscle.
- **Phase 3: First real workflow (weeks 3-4)** — Use it for one real workstream end-to-end (e.g. a 1:1 prep + digest + follow-up cycle). Find your first "this saves me an hour" moment.
- **Phase 4: Make it yours (week 5+)** — First memory corrections, first skill you ask Cameron/Albert to build for you, first time you teach your COS something Cameron's doesn't know.
- **Honest expectations callout:** the first week feels awkward. By week 3 it clicks. By month 2 you'll wonder how you worked without it.

### 9. QUICK REFERENCE

- Starter slash commands cheat sheet
- Where to ask for help (Cameron DM, Shared Context Board, the COS itself with "how do I...")
- Link to the onboarding repo
- Names of the agents already in the network

---

## Feedback

Wire the Suggest Widget (`_shared/suggest-widget/widget.js`) into the artifact. Suggestions land in the existing `#tool-feedback` Slack channel — no new channel needed.

---

## What to Leave Out (so the deck doesn't bloat)

- Don't try to teach Markdown, the terminal, or git. If they need it, the COS will show them in-flow.
- Don't list every skill — the catalog grows weekly. Point to `/commands` for the live list.
- Don't pitch ROI numbers. The point is the experience, not a business case (this audience is already bought in — Cameron is rolling them out as their CEO).

---

## Flag Before Building

**The Anthropic Org Setup Checklist tool currently only lives at `localhost:8110` — not deployed publicly.** Either:

- (a) Cameron deploys it to a public GitHub Pages URL before this artifact ships, or
- (b) the Phase 1 CTA points to a placeholder until that URL exists.

Confirm with Cameron which path before wiring the link.

---

## Done Criteria

1. All 9 sections present, ordered, with content matching this brief's spec
2. Non-technical body copy with collapsible "under the hood" depth for Matisen + Paul
3. Cameron's voice — no AI tells (read voice section above + run filter before declaring done)
4. Mobile QA clean at 360 / 414 / 768 / 1024 / 1440px (sidebar hamburger functional, cards stack)
5. Suggest Widget firing to `#tool-feedback` (test the webhook before declaring done)
6. Phase 1 CTA wired to Anthropic Org Setup Checklist (confirm URL with Cameron before linking)
7. Deployed live to new `einsteinadmin/` GitHub Pages repo with obfuscated URL + `noindex/nofollow` + `robots.txt` disallow
8. Link returned to Cameron

Flag any open questions back before building.
