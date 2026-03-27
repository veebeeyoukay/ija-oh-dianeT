# UT Pre-Med AI Dashboard

A single-file, browser-based dashboard for a University of Tampa pre-med biology student navigating their AI learning journey, research opportunities, networking, and campus life.

Built with zero dependencies — pure HTML, CSS, and vanilla JavaScript. All state is persisted in browser `localStorage`. No server, no build step, no accounts required beyond the included login.

---

## Live Demo

Deploy your own in one click via the Netlify button, or clone and open `dashboard.html` directly in a browser.

---

## Features

| Tab | What it does |
|-----|-------------|
| **Action Plan** | 13 checkable tasks pulled from the original action plan spreadsheet. Progress persists across sessions. |
| **Learning** | Weekly 3×30-min schedule tracker with session counter, plus a full AI learning path roadmap and course resources. |
| **Networking** | Moffitt Cancer Center ML & Bioinformatics faculty targets, Tampa Bay AI community resources, Moffitt volunteer/shadowing pipeline. |
| **Rowing** | UT Women's Rowing walkthrough — coach contact, step-by-step path from novice to varsity tryouts. |
| **LinkedIn** | Headline formula, profile checklist with persistent checkboxes, and quick tips for building a pre-med AI brand. |
| **Notes** | Free-form notepad saved to localStorage. |

**Other highlights:**
- Login screen backed by `localStorage` — session persists across page reloads
- UT navy & gold color theme with rowing wave animation
- Responsive layout for desktop and iPhone 16 (and all modern mobile browsers)
- Live stats in the hero banner (tasks done / remaining)

---

## Getting Started

### Option 1 — Open directly (no server needed)

```bash
git clone https://github.com/veebeeyoukay/ija-oh-dianeT.git
cd ija-oh-dianeT
open dashboard.html   # macOS
# or double-click dashboard.html in Finder / Explorer
```

### Option 2 — Local HTTP server (avoids any browser file:// quirks)

```bash
# Python 3
python3 -m http.server 8080
# then open http://localhost:8080/dashboard.html
```

```bash
# Node (if you have npx)
npx serve .
```

---

## Deploying to Netlify

The repo includes a `netlify.toml` that configures Netlify to serve the site from the root with all routes pointing to `dashboard.html`.

### Via Netlify UI

1. Push this repo to GitHub (already done if you're reading this).
2. Log in to [netlify.com](https://netlify.com) → **Add new site → Import an existing project**.
3. Connect your GitHub account and select this repository.
4. Netlify will auto-detect `netlify.toml` — no build command or publish directory changes needed.
5. Click **Deploy site**. Done in seconds.

### Via Netlify CLI

```bash
npm install -g netlify-cli
netlify login
netlify deploy --prod --dir .
```

---

## Login Credentials

The dashboard uses a simple hardcoded credential map stored in the JavaScript. This is intentional — the app is entirely client-side with no backend, so the login is a lightweight access layer, not a security boundary.

| Username | Password |
|----------|----------|
| `diane` | `spartan2029` |
| `admin` | `password` |

### Changing or adding credentials

Open `dashboard.html` and find this block near the bottom:

```javascript
const CREDS = { 'diane': 'spartan2029', 'admin': 'password' };
```

Add entries or change passwords directly. Usernames are case-insensitive (lowercased on input).

> **Note:** Do not use this login mechanism to protect genuinely sensitive data. localStorage is readable by anyone with access to the browser's developer tools.

---

## Customizing for a Different Student

This dashboard was built for a specific student's roadmap, but it's easy to adapt:

1. **Tasks** — Edit the `TASKS` array in the `<script>` block. Each task has `id`, `name`, `priority`, `deadline`, and `status`.
2. **LinkedIn checklist** — Edit the `LINKEDIN_ITEMS` array.
3. **Networking targets** — Edit the HTML in `#tab-network` directly.
4. **Schedule** — Edit the schedule day rows in `#tab-learn`.
5. **Colors** — Change `--ut-navy` and `--ut-gold` in the `:root` CSS block to match any school's colors.
6. **Branding** — Update the topbar brand text and hero copy.

---

## Project Structure

```
.
├── dashboard.html    # Entire app — HTML + CSS + JS in one file
├── netlify.toml      # Netlify publish config
├── .gitignore        # Excludes .DS_Store
└── README.md         # This file
```

Source documents (`.docx` / `.xlsx`) used to build the dashboard content are kept locally and not committed to the repository.

---

## Tech Stack

- **HTML5** — semantic structure
- **CSS3** — custom properties, grid, flexbox, keyframe animations
- **Vanilla JavaScript** — no frameworks, no dependencies
- **localStorage** — all user state (task checks, notes, progress, session)

---

## Contributing / Forking

Fork freely. If you adapt this for another student or institution, the main things to update are the `TASKS` array, the networking tab HTML, and the `:root` color variables.

Pull requests welcome for bug fixes or accessibility improvements.

---

## License

MIT — use it, fork it, adapt it.

---

*Built with [Claude Code](https://claude.ai/claude-code) · University of Tampa Spartans · Go Spartans 🚣*
