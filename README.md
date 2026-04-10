# ⚽ KICKOFF — Live Football Dashboard

A sleek, dark-themed football dashboard powered by free football APIs via RapidAPI.
No build tools, no frameworks — pure HTML/CSS/JS, just open and go.

---

## 🚀 Quick Start

1. **Download** `kickoff.html`
2. **Open** it in any browser — done. No server required.

> ⚠️ You need an active [RapidAPI](https://rapidapi.com) account with the APIs subscribed (both free).

---

## 🔑 API Setup

The dashboard uses **two free RapidAPI APIs**. Replace the key in the `<script>` block:

```js
const RAPIDAPI_KEY = 'YOUR_RAPIDAPI_KEY_HERE';
```

### APIs Used

| API | Purpose | Free Tier |
|---|---|---|
| [API-Football v1](https://rapidapi.com/api-sports/api/api-football) | Standings, player stats, team search | 100 req/day |
| [Free API Live Football Data](https://rapidapi.com/heisenbug/api/free-api-live-football-data) | Live scores, today's matches, upcoming | 100 req/day |

### How to get your key
1. Go to [rapidapi.com](https://rapidapi.com) and create a free account
2. Subscribe to **both** APIs above (both have free plans)
3. Copy your API key from any API page → paste into `kickoff.html`

---

## ✨ Features

### 📺 Matches
- **Live tab** — All currently playing matches with real-time scores and minute
- **Today tab** — All fixtures scheduled for today
- **Upcoming tab** — Next round of fixtures across competitions
- Live match cards glow red with a pulsing LIVE indicator
- Graceful demo preview when no matches are live (off-season or no quota)

### 🏆 Standings
- Full league table with MP / W / D / L / GF / GA / GD / Pts
- Switch between **Premier League, La Liga, Serie A, Bundesliga, Ligue 1**
- Team logos, colour-coded stats (wins in green, losses in red)
- Clickable from sidebar league list

### 🔍 Search
Three search modes:
- **Players** — Rich data from API-Football: goals, appearances, nationality, age
- **Teams** — Club details: founded year, venue name, country
- **Leagues** — League type, country

### 📊 Dashboard Sidebar
- Live match count + today's fixture count
- Top 6 leagues with one-click standings
- API connection status indicator

---

## 🎨 Design System

| Token | Value | Usage |
|---|---|---|
| `--pitch` | `#00C853` | Primary accent (goals, active states) |
| `--red` | `#FF3333` | Live matches, errors |
| `--amber` | `#FFB800` | Today's fixtures count |
| `--bg` | `#0a0a0f` | Page background |
| `--card` | `#1c1c25` | Card surfaces |

**Fonts used:**
- [Bebas Neue](https://fonts.google.com/specimen/Bebas+Neue) — Display headings, scores
- [DM Sans](https://fonts.google.com/specimen/DM+Sans) — Body text, UI
- [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) — Stats, labels, badges

---

## 📁 File Structure

```
kickoff.html        ← single-file app, everything included
README.md           ← this file
```

No dependencies. No npm. No bundler.

---

## ⚙️ Configuration

You can tweak these constants at the top of the `<script>` block:

```js
const SEASON = 2024;   // Change to current season year
```

---

## 🔒 Rate Limits

Both APIs are free with **100 requests/day** on RapidAPI.

The dashboard makes at most **3 requests on load**:
- 1 × live matches
- 1 × today's fixture count
- Standings only on tab switch

Search requests are **debounced** (700ms) to avoid burning quota.

---

## 🛠️ Extending

### Add a new league to Standings
Find the league ID on API-Football, then add a tab:

```html
<button class="tab" onclick="loadStandings(YOUR_LEAGUE_ID,'League Name',this)">Name</button>
```

### Change the colour scheme
Edit the `:root` CSS variables at the top of the `<style>` block.

---

## 📜 License

MIT — free to use, fork, and modify.

---
