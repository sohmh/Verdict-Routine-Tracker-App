# VERDICT
### *Quantifying the quality of time spent*

A minimalist daily routine tracker that scores your day on a 0–10 scale and delivers a verdict on how well you spent your time — from *Abysmal* to *Transcendent*.

---

## What it does

VERDICT lets you build structured daily routines and track your completion of them over time. It then scores your performance using a scoring formula that accounts for both *how many* tasks you completed and *how many you left behind*, aggregating those scores into weekly, monthly, and yearly averages.

---

## Panels

**Routines** — Build and manage named routines. Each routine is a sequenced list of tasks displayed as a flowchart. Every task carries a title, start time, duration, and description.

**My Day** — Select a routine for the day and tick off tasks as you complete them. A live progress bar tracks your completion. Data is saved automatically.

**Stats** — View your Day, Week, Month, and Year scores for any selected date, each paired with a qualitative verdict title. A history log shows all past days with their scores.

---

## Scoring Formula

```
D = (p/t)^(1 + n/t) × 10
```

| Variable | Meaning |
|----------|---------|
| `p` | Tasks completed |
| `t` | Total tasks in routine |
| `n` | Tasks not completed (`t - p`) |

The exponent `(1 + n/t)` is dynamic — it grows as incompletion increases, making the penalty progressively harsher the more tasks you skip. A perfect day always scores **10.0**. A day where nothing is done scores **0.0**.

Weekly, Monthly, and Yearly scores are arithmetic averages of their constituent daily scores.

---

## Verdict Titles

| Score Range | Verdict |
|-------------|---------|
| 0.0 – 1.4 | Abysmal |
| 1.5 – 2.4 | Dismal |
| 2.5 – 3.4 | Miserable |
| 3.5 – 4.4 | Lackluster |
| 4.5 – 5.4 | Mediocre |
| 5.5 – 6.4 | Decent |
| 6.5 – 7.4 | Pleasant |
| 7.5 – 8.4 | Gratifying |
| 8.5 – 9.4 | Exhilarating |
| 9.5 – 10.0 | Transcendent |

---

## Tech

- Single-file vanilla HTML / CSS / JavaScript — no frameworks, no dependencies, no build step
- Data persisted via `localStorage`
- Fonts loaded from Google Fonts (Cinzel + Jost), with Warbler Banner Regular as the preferred display font if available locally

---

## Running it

Just open `VERDICT-routine-tracker.html` in any modern browser. No server required.

```bash
# Clone the repo
git clone https://github.com/yourusername/verdict.git

# Open directly
open VERDICT-routine-tracker.html
```

---

## Converting to Android APK

The app is structured for straightforward wrapping with [Capacitor](https://capacitorjs.com/):

```bash
npm install @capacitor/core @capacitor/cli
npx cap init
npx cap add android
# Copy the HTML file into the web root, then:
npx cap open android
```

---

## Design

- **Palette:** Black backgrounds, dark purple accents (`#5b21b6`, `#7c3aed`, `#a78bfa`)
- **Typography:** Warbler Banner Regular (display) / Jost (body)
- **Philosophy:** Minimalist, data-forward, no clutter

---

*Designed and specced by [Your Name]. Built with AI-assisted development.*
