# Bot Dashboard: shared record

Read this before working on the panel. Whoever changes the panel adds one dated line to the Change log.

## What it is
Lee's live dashboard of his bot team: https://leepurcell-cpu.github.io/Botmap/
Repo leepurcell-cpu/Botmap (GitHub Pages). Source /workspace/botmap/src. Build: run `python3 make_data.py`, `python3 mkconn.py` then `python3 build_site.py` in src, copy site/* to /workspace/Botmap-pub, pull, commit, push.
Tabs: Map, Connections, Mind map, Marketing team (marketing.html; nextteam.html redirects), How it's built.

## Who does what
- Lee can go to Dr Eggbot or CTO for panel, structure or design work. Both read this file so work carries over.
- Dr Eggbot (1abf2bad-9f9e-42a1-8268-cd552b4b6394): bot structure, bot instructions and panel design. Makes all bot changes with Lee's yes.
- CTO (159a74de-62e0-4573-8c7d-a6c5e5cb4152): can plan panel builds when Lee comes to it; check this file and tell Dr Eggbot about anything that changes bot structure.
- Bot Dashboard (8b1f84e7-4e03-4685-90ec-d8ef0ca10238): keeps the panel current; routine updates go straight to Senior Developer.
- Senior Developer (8f3eaf69-337e-4c6a-861c-7582d48747d0): builds and publishes. Standing approval for Botmap changes Lee asked for.
- Bot Auditor (e17f235c-c66b-4b8d-a8d7-bb02960cd2a1): runs the real checks and reports to Dr Eggbot. The panel is a visual of the team only.

## Design decisions (keep)
- Font Inter everywhere. Lee dark indigo #312E81; Non Stop flat indigo #4F46E5 (no gradient), labelled Chief of Staff and the hub.
- Two kinds of bots: Role (whole job) and Expert (one task); every bot card shows its type; counts must stay right.
- Header collapsible, open on first visit, shared localStorage key bcpHeaderCollapsed; indigo Hide header button.
- No Data stores or Dr Eggbot coverage buttons in the header.
- Show display name 'Bot Auditor' (profile name; not 'Alfred Bot Auditor'). Other display names: 'Risk & Compliance', '2nd Opinion (Bounce)'; no 'Claude Check' label. Strip secrets only; emails and client names are fine.
- Four group colours (set in make_data.py GROUP, drawn in template.html, mindmap.html, build_site.py): Bot Team purple #7C3AED (Dr Eggbot central, Bot Dashboard, Bot Auditor); Leaders and Senior Staff blue #2563EB (CFO, CMO, CTO, Risk & Compliance, Projects Manager, Deal Desk as Role bot titled 'Deal Analyst'); Skills white cards, slate accent #64748B (Senior Developer, Collabor8 Studio, Figma Bro); Collabor8 Routine green #0e9f77 (Scout, MNO Research, Micro Insurance, Name Check, Boardy Rolodex, Work Brain, 2nd Opinion, Meeting Brief). Small heading: Night Time Automations (Night Prospects). Role/Expert tags take the group colour; green 'Research feeds Non Stop' label.
- Data refresh: run `python3 make_data.py` in src before the build to re-read profiles (labels, titles, verbatim instructions).
- No Gaps & overlaps section on the panel; Dr Eggbot checks weekly and reports to Lee in chat.
- Every change: no clipping or overlap at 390, 1024 and 1280 before publishing.

## Revert
Tag `pre-refresh-2026-10-10` marks the live site before the 10 Oct 2026 light refresh (commit 25882df). One-step restore, in /workspace/Botmap-pub (new commit, no history rewrite):
`cd /workspace/Botmap-pub && git pull && git checkout pre-refresh-2026-10-10 -- . && git commit -m 'Revert to pre-refresh' && git push`
Source files from before the refresh are in /workspace/botmap/bak-2026-10-10/ (copy back into src to rebuild the old version).

## Change log
- 16 Oct 2026: Rhiannon renamed Non Stop everywhere (id cd84d18c unchanged; make_data.py NAME2ID maps the Non Stop profile). Lee's skills are exactly 8 (automation, bot-rules, claude, data-dashboard, design, report-writing, setup-fill, thought-leadership), re-synced from workflows SKILL.md; consultancy-agreement, project-tracker, web-build, astronaut and marketing-playbook no longer listed; all counts derive from data.json. 3D mind map: hover (desktop) or tap (phone/touch) a bot shows who it works with and dims the rest; tap again or outside to clear
- 11 Oct 2026: Skill count checked: Bots page "5 main skills" is correct (5 myskill-collabor8 SKILL.md incl. bot-rules; My skills/Myskills are helpers); Connections "Skills in use 6" counts the 5 plus My skills / Myskills. Front-page skills row and Connections skills card screenshot-checked at 390, 1024, 1280: no clipping or overlap, no code change
- 11 Oct 2026: added myskill-collabor8-bot-rules skill (master bot rules)
- 11 Oct 2026: Verbatim instructions refreshed for all 21 bots after routing/gating removal; card text, notes, map labels and change notes updated to match (CTO is the tech sounding board, not front door or tech lead; Senior Developer builds for whoever briefed it; Figma Bro hands specs to Senior Developer whenever it helps; Bot Auditor builds to whoever fits; brief whoever fits)
- 11 Oct 2026: Routing rules removed to match the bots: What stays fixed now has one guardrail (Non Stop is the only writer of Notion Notes); builds-through-CTO and changes-through-Dr-Eggbot wording removed from How the team works, story steps, principles and notes; Lee picks where work starts and any bot can call CTO, Senior Developer or any colleague directly
- 11 Oct 2026: Consultant & Analyst, Strategic Partner Prep, the Nothing Dropped room and the Partner call prep skill removed from the panel (Lee deleted them): make_data.py DROP adds analyst, spp, room_nd; Teamwork lane/box and skill pill removed from the org chart, map, mind map and story; stale change notes filtered. Now 22 bots, 64 hand-offs, 2 on a schedule
- 11 Oct 2026: How the team works, org chart notes, story and principles updated for the generic teamwork model (any bot can call any teammate or skill; where Lee starts is where he finishes; owner chases; bot given work reports back; guardrails: builds other bots start go through CTO, routine Bot Dashboard updates excepted, bot changes via Dr Eggbot, Non Stop writes Notes). Chain-of-command and 'go through the leaders' wording removed; Brand & Design Studio used throughout (incl. Marketing tab); verbatim instructions refreshed for all 21 bots
- 11 Oct 2026: HAND-OFFS loop added to all 21 bots
- 11 Oct 2026: How the team works gets a Hand-offs section (where Lee starts is where he finishes; the bot that hands work out owns and chases it; the bot given work reports back to whoever asked); What stays fixed now says Non Stop hears about anything worth keeping (Lee approved)
- 11 Oct 2026: Skills in use now matches Lee's own skills (myskill-collabor8-design, thought-leadership, marketing-playbook, astronaut, My skills / Myskills); strategic-partner-call-prep removed everywhere, Meeting Brief handles first meetings in its normal brief; org chart gets a Shortcut skills (type /myskill) row under Experts and skills (Senior Developer)
- 10 Oct 2026: team combinations byline added (Dr Eggbot)
- 10 Oct 2026: hand-offs count checked; group rooms tile replaced with a line on groups (Dr Eggbot)
- 10 Oct 2026: What stays fixed updated for Non Stop's role (Dr Eggbot)
- 10 Oct 2026: Routines in the background added to How the team works (Dr Eggbot)
- 10 Oct 2026: How the team works rewritten around org chart plus free-flowing work (Dr Eggbot)
- 10 Oct 2026: How the team works section added to front page (Dr Eggbot)
- 10 Oct 2026: Bot Auditor display name set to profile name 'Bot Auditor' (not 'Alfred Bot Auditor'); make_data.py DISPLAY mapping updated. Recruiting Coordinator (68f1d893) removed from the panel (Lee deleting; make_data.py DROP). Skills lane now Senior Developer, Collabor8 Studio, Figma Bro. Now 22 bots.
- 10 Oct 2026: Consultant & Analyst (81786e2f) and Strategic Partner Prep (1fc3ae5d) removed from the panel, plus the Nothing Dropped room and Teamwork heading (make_data.py DROP; profiles left untouched). Their edges (Projects Manager tasks, CFO/Risk referrals, research-bot deal work, Collabor8 Studio documents) now go to Deal Desk, which moves to Leaders and Senior Staff as a Role bot titled 'Deal Analyst' (REVIEW and STRUCTURE modes). Meeting Brief does partner call prep with shared skill strategic-partner-call-prep (added to Skills in use). All verbatim instructions refreshed from current profiles; 'Bot Auditor' profile name mapped to Alfred. Now 23 bots, 0 rooms. Mind map preview image regenerated. Backup of prior source: bak-2026-10-10b/.
- 10 Oct 2026: Renamed group heading 'Leadership' to 'Leaders and Senior Staff' on Map, Mind map, How it's built, mobile headings and legends (blue colour and members unchanged).
- 10 Oct 2026: Boardy Rolodex subtitle corrected to 'Boardy CRM' (removed typo 'Boardly' from the live site). Profile left unchanged; make_data.py strips Boardly→Boardy on title refresh.
- 10 Oct 2026: Light refresh (Lee approved 20:41): four colour groups (Bot Team, Leadership, Skills, Collabor8 Routine) on Map, Mind map (incl. mobile preview image) and How it's built; Teamwork and Night Time Automations headings; group-coloured Role/Expert tags; green 'Research feeds Non Stop' label; group headings on mobile. Names: Alfred Bot Auditor, Risk & Compliance, Nothing Dropped, 2nd Opinion (Bounce); 'Claude Check' dropped. Subtitles refreshed from profile titles; Deal Desk set as Expert; all verbatim instructions refreshed from current profiles. Revert tag pre-refresh-2026-10-10.
- 10 Oct 2026: Renamed the live site from Bots Control Panel / Bot Control Centre / Bot Map to Bot Dashboard throughout (page titles, headers, nav, body text, data.json bot name for id 8b1f84e7-4e03-4685-90ec-d8ef0ca10238, and make_data.py name lookup). Verbatim instructions refreshed for CTO, Senior Developer, Projects Manager, Non Stop and Bot Dashboard. URL and repo unchanged (Lee approved).
- 10 Oct 2026: Two kinds of bots section; Role/Expert tags; renamed Bot Dashboard; Who runs this panel box; tab order; Collabor8 Studio and CMO added; collapsible header; Marketing team tab replaces Next team (Dr Eggbot).
- 10 Oct 2026: Gaps & overlaps cleaned (removed stale 'Bot Auditor and Bot Dashboard hand big builds to Senior Developer'; titles item now CMO, Consultant & Analyst, Recruiting Coordinator); Bot Auditor → CTO for builds, Bot Dashboard → Senior Developer (routine) and Dr Eggbot or CTO (design/structure) on the map; verbatim instructions refreshed for Bot Dashboard, CTO, CMO and Senior Developer.
- 10 Oct 2026: Gaps & overlaps section removed from the panel (Map sidebar and mobile overview); replaced with one line: 'Gaps and overlaps are checked weekly by Dr Eggbot and reported to Lee in chat.' make_data.py no longer generates the list (oddities=[]); Who runs this panel: Bot Auditor now 'checks the bots and reports problems to Dr Eggbot' (Senior Developer).
- 10 Oct 2026: Bot Dashboard Description instructions refreshed word-for-word from its current profile (Bot Auditor runs the real checks; panel is a visual of the team only). Who does what: Bot Auditor line updated to match.
