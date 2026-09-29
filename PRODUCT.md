# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

Players of the "Shadow of the Colossi" Daggerheart campaign, plus their GM. A small, trusting table (roughly five people). Players use it both at the table during sessions (quick entries on phones) and between sessions (longer writing and planning on laptops).

## Product Purpose

A player-facing companion to the campaign wiki. Players keep a shared journal (entries readable by the whole party, editable by their author or the GM) and track party quests, assigning each to one player or the whole party. The GM sees and edits everything. Success: players actually use it to remember what happened and what they are chasing, instead of scattered chats and paper.

## Positioning

It lives inside the campaign's own wiki: the journal and quest log sit beside the lore pages the GM publishes, so the party's record and the world's record are one place.

## Operating Context

- Embedded as an iframe in two Quartz wiki pages (`content/Journal.md`, `content/Quests.md`; the old Party Notes / Objectives URLs redirect via aliases), served from `quartz/static/party/index.html` on GitHub Pages.
- Follows the wiki's light/dark toggle at runtime, with its own survey-sheet palette.
- Data in Firebase (Firestore + email/password auth, usernames mapped to `<user>@party.local`). Party roster in the Firestore `members` collection.
- Public read by default; writing needs login. A `requireLogin` flag plus `firestore.login.rules` switch to members-only with private quests.

## Capabilities and Constraints

- Journal: many entries per player, markdown (sanitized) rendering, autosave plus explicit Save, filter by player.
- Quests: add, tick off, assign to a player or the whole party, reassign by any logged-in player, filter by player; private quests only in login-only mode.
- Login: pick your name from a roster dropdown plus a password.
- Must stay a single static HTML file with CDN imports (no build step); GitHub Pages caches files for 10 minutes.
- Free-tier Firebase; no server code.

## Brand Commitments

- Campaign name: "Shadow of the Colossi". World: the realm of Ecerah; colossal beings, the sealed god-prophet Vodarr.
- Terminology: say **Quests**, not "objectives"; say **Journal** (and journal entries), not "notes".
- The user chose a campaign-flavoured look for this app, distinct from the surrounding wiki.

## Evidence on Hand

- Campaign intro copy and art: `content/index.md`, `content/undead-giant4_o.jpg`.
- No other brand assets exist; do not invent lore beyond the intro.

## Product Principles

1. Fast at the table: adding or ticking a quest, or jotting an entry, is one or two actions on a phone.
2. The party's shared record: everyone can read everything that is not private; authorship is always visible.
3. Stay out of the way of play: no ceremony, no gamification.
4. Free and self-maintained: the GM manages everything from the Firebase console, with no redeploys for roster changes.
