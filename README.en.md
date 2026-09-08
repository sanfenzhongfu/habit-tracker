# Habit Tracker · 习惯打卡

A habit tracker so light it hurts. **One single HTML file** — no install, no build, no dependencies. Just double-click it.

Live demo: https://sanfenzhongfu.github.io/habit-tracker/
English version: https://sanfenzhongfu.github.io/habit-tracker/en/

A language switch sits in the top-right corner of the page. Both versions share the same check-in data.

[简体中文](./README.md) | English

---

## Features

- **Check in** — tap a habit card to mark today done; tap again to undo
- **Progress ring** — the ring up top shows today's completion ratio
- **Streaks** — automatic count of consecutive days per habit; 7+ days gets a "looking good" badge
- **Last 7 days** — a bar chart of the past week, plus completion rate and perfect-day count
- **All done** — a brief confetti burst when everything is checked off
- **Customizable** — name, icon and color are all editable; habits can be deleted
- **Rollover** — leave the page open past midnight and it refreshes into the new day automatically

## Usage

### Online

Open the link above in any browser — phone, tablet or desktop.

Worth adding to your home screen so it behaves like an app:
- **iPhone**: Safari → Share → *Add to Home Screen*
- **Android**: Chrome → menu → *Add to Home Screen*

### Local

Download `index.html` and double-click it.

---

## Where your data lives

**Data is stored only in your own browser** (localStorage). Nothing is uploaded, no account, no sign-in.

| Situation | What happens |
| --- | --- |
| Close and reopen the page | Data is still there |
| Open in a different browser | Previous data is not visible |
| Phone and computer separately | The two do not sync |
| Clear browsing data / private mode | **Data is lost** |

So pick one browser on one device and stick with it.

Cross-device sync would require a backend and user accounts — this project is pure frontend and deliberately has neither.

---

## Project structure

```
.
├── index.html      # Chinese version: HTML + CSS + JavaScript in one file
├── en/
│   └── index.html  # English version
├── README.md       # 简体中文
├── README.en.md    # English
└── LICENSE         # MIT
```

No dependencies, no build step, no framework. Edit, save, refresh.

Data format: a single JSON object under the localStorage key `habit-tracker-v1`, containing `habits` (the habit list) and `records` (check-ins indexed by date).

---

## Development

```bash
git clone git@github.com:sanfenzhongfu/habit-tracker.git
cd habit-tracker
open index.html
```

Branches:
- `main` — stable; GitHub Pages publishes from here
- `dev` — development

> **Note**: if you are behind a proxy or VPN, SSH port 22 may be blocked.
> This project is configured to use port 443 instead (see `~/.ssh/config`).

## Design notes

Deliberately restrained: near-black canvas, hairline borders, a single champagne accent, no saturated gradients or bouncy effects. All motion uses one spring curve — `cubic-bezier(.22, 1, .36, 1)`.

---

## Roadmap

- Export / import data (so a cleared cache is not fatal)
- Monthly heatmap view
- Reorder and archive habits
- Reminder notifications

## License

MIT — do whatever you want with it.
