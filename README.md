# GitHub Breakout — Playable on Your Profile

A real Breakout game built from your GitHub contribution graph.
Each green square becomes a brick. Break them all.

---

## Live Demo

**[PLAY NOW](https://YOUR_USERNAME.github.io/github-breakout/)**

---

## Setup (5 minutes)

### Step 1 — Create a new repository

Create a repository named **`github-breakout`** on your GitHub account.
(It can be public or private — GitHub Pages requires public on free plans.)

### Step 2 — Add the files

Copy these files into your new repository:

```
github-breakout/
├── .github/
│   └── workflows/
│       └── deploy.yml      ← GitHub Action
└── game/
    └── index.html          ← The game
```

### Step 3 — Enable GitHub Pages

1. Go to your repository → **Settings** → **Pages**
2. Under **Source**, select **Deploy from a branch**
3. Choose branch: **gh-pages** / folder: **/ (root)**
4. Click **Save**

### Step 4 — Run the Action

Go to **Actions** tab → **Deploy GitHub Breakout Game** → **Run workflow**

This will:
- Fetch your last 365 days of contributions via GraphQL
- Save them as `contributions.json`
- Deploy the game to `https://YOUR_USERNAME.github.io/github-breakout/`

The action runs automatically every day at midnight to keep data fresh.

### Step 5 — Add to your profile README

Paste this into your profile `README.md`
(the repo named the same as your GitHub username):

```markdown
## Play Breakout with my GitHub contributions!

[![GitHub Breakout](https://img.shields.io/badge/🎮_PLAY-GitHub_Breakout-39d353?style=for-the-badge&labelColor=0d1117)](https://YOUR_USERNAME.github.io/github-breakout/)

> Click the badge above to break all my commits!
```

Replace `YOUR_USERNAME` with your actual GitHub username.

---

## How it works

```
GitHub GraphQL API
      ↓
Contribution data (365 days)
      ↓
contributions.json (committed to repo)
      ↓
GitHub Pages hosts the game
      ↓
Game reads JSON on load → builds brick grid
      ↓
Your profile README links to the live game
```

- Bricks colors match your exact GitHub contribution graph
- Ghost bricks (0 commit days) become real bricks in Level 2+
- Combo multiplier, 5 power-ups, multi-ball, laser mode
- High score saved in browser localStorage
- Works on mobile with touch controls
- No external dependencies — pure HTML/CSS/JS

---

## Brick Color Key

| Level | Commits / day | Color |
|-------|--------------|-------|
| 0 | 0 | Ghost (dim) |
| 1 | 1–4 | Dark green |
| 2 | 5–9 | Medium green |
| 3 | 10–19 | Bright green |
| 4 | 20+ | Vivid green |

---

## Controls

| Key | Action |
|-----|--------|
| Mouse | Move paddle |
| ← → or A D | Move paddle |
| Space or Click | Launch ball |
| P | Pause |
| R | Restart |
| M | Mute |

---

## Power-ups

| Symbol | Effect |
|--------|--------|
| W | Wide paddle for 9 seconds |
| S | Slow ball |
| ♥ | +1 Life |
| M | Multi-ball (3 balls) |
| L | Laser mode for 7 seconds |

---

## Updating contribution data

The GitHub Action runs every day automatically.
To update manually: **Actions → Deploy GitHub Breakout Game → Run workflow**
# github-breakout2
