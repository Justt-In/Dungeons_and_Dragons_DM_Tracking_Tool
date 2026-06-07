# ⚔ DM Codex — D&D Campaign Tracker

A fully-featured, browser-based Dungeon Master tool. No server required — runs entirely in your browser via GitHub Pages.

**Live site:** `https://YOUR-USERNAME.github.io/YOUR-REPO-NAME`

---

## Features

| Tab | What it does |
|-----|-------------|
| **Ideas** | Track plot hooks, NPCs, locations, items, encounters and lore with status tracking |
| **Generate** | AI-powered idea generator (Claude) for any category |
| **Mind Map** | Drag-and-drop canvas with super nodes, collapsible children, node notes, and connection lines |
| **Sessions** | Upload audio recordings (auto-transcribed via Whisper) or paste transcripts; Claude extracts entities and summaries |
| **Players** | Full character sheets — manual entry or auto-import from D&D Beyond PDF |
| **Combat** | Full initiative tracker with HP, AC, conditions, death saves, damage log, and round counter |

---

## Setup

### 1. Fork or upload to GitHub

Upload `index.html` and `README.md` to a new GitHub repository.

### 2. Enable GitHub Pages

1. Go to your repo → **Settings** → **Pages**
2. Source: **Deploy from a branch**
3. Branch: `main` / `root`
4. Save — your site will be live at `https://YOUR-USERNAME.github.io/REPO-NAME` within ~60 seconds

### 3. Add your API keys (in-app)

Keys are stored locally in your browser and never sent anywhere except the respective APIs.

| Key | Where to get it | Used for |
|-----|----------------|---------|
| **Anthropic** | [console.anthropic.com](https://console.anthropic.com) | Ideas generation, session analysis, character sheet reading |
| **OpenAI** *(optional)* | [platform.openai.com](https://platform.openai.com) | Audio transcription via Whisper. If omitted, paste transcripts manually |

---

## Storage

The app tries **IndexedDB** first (unlimited, shown as green badge in header), falling back to **localStorage** (~5MB limit, gold badge). Both are local to your browser.

**To sync between devices:** use the **Export** button (saves a `.json` file) and **Import** on the other device.

---

## Sessions — Audio Transcription

1. Record your session (any recorder app — Voice Memos, Audacity, OBS, etc.)
2. Export as MP3, WAV, M4A, or WEBM (max 25MB for Whisper)
3. Drop the file onto the Sessions tab — it transcribes automatically, then Claude extracts NPCs, locations, items, factions, events and a full narrative summary
4. Entities are added to your codex and you're walked through placing them on the Mind Map

**No OpenAI key?** Click *"Paste a transcript manually"* instead.

---

## D&D Beyond Character Sheets

1. On D&D Beyond, open a character → **Export to PDF** (or print to PDF)
2. In the Players tab, click **Upload D&D Beyond sheet**
3. Claude reads the PDF and fills in name, class, subclass, race, ability scores, AC, HP, spells, equipment, and proficiencies automatically

---

## Combat Tracker

- **Add to combat** from any player card, or type a monster name in the combat panel
- Click **Start combat** to begin — turns advance in initiative order
- Click condition badges (Blinded, Charmed, etc.) to toggle them on/off
- Use **+/−** buttons to deal damage or heal with a logged entry
- Death saves appear automatically when a creature hits 0 HP
- **Collapse** shrinks the tracker to a minimal list; expand for full detail

---

## Multiple Campaigns

Use the dropdown in the header to switch campaigns. Each campaign has its own ideas, sessions, map, players, and combat state. Create, rename, or delete campaigns from the header.

---

## Updating

To update the app, simply replace `index.html` in your GitHub repo with the new version. Your data is stored in your browser — it is **not** in the HTML file, so replacing the file will not affect your saved campaigns.

---

## Privacy

- All data stays in your browser (IndexedDB / localStorage)
- API keys are stored locally and sent only to Anthropic / OpenAI
- No analytics, no tracking, no ads
