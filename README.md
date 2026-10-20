# 🐍 Snake Game

A classic Snake game that runs entirely in the browser — one single HTML file, no build step, no dependencies. Built to be played on both desktop and mobile.

[![Play Now](https://img.shields.io/badge/%E2%96%B6_Play_Now-Snake_Game-brightgreen?style=for-the-badge)](https://shuangjielv.github.io/Snake-game/)

**▶️ Play it live: https://shuangjielv.github.io/Snake-game/**

![Built with](https://img.shields.io/badge/built_with-HTML%20%2F%20CSS%20%2F%20JavaScript-green) ![Dependencies](https://img.shields.io/badge/dependencies-none-blue)

## ▶️ Play

**Option 1 — play online:** https://shuangjielv.github.io/Snake-game/ (GitHub Pages)

**Option 2 — just open the file:** download `index.html` and open it in any modern browser (Chrome, Safari, Edge, Firefox).

On iPhone/iPad, open the page in Safari and choose **Share → Add to Home Screen** to play it like a native app.

## 🎮 Controls

| Input | Action |
| --- | --- |
| Swipe on the board | Steer the snake |
| On-screen arrow buttons | Steer the snake |
| Arrow keys / WASD | Steer the snake |
| Spacebar | Pause / resume |

## ✨ Features

- 20×20 grid rendered on `<canvas>`, with a drawn snake head (eyes included)
- Score tracking (+10 per food) and a persistent best score via `localStorage`
- Speed ramps up as you eat — the game gets faster the longer you survive
- Start / pause / resume / restart states with an overlay UI
- Responsive layout that fits phone screens without horizontal scrolling
- Dark UI theme, zero external assets — everything is inline in one file

## 🛠️ How it works

The whole game is a small loop built from five pieces:

1. **State** — the snake is an array of `{x, y}` grid cells, head first.
2. **Move** — on each tick (`setInterval`), add a new head in the current direction and drop the tail.
3. **Food** — spawn on a random free cell (re-roll if it lands on the snake).
4. **Eat** — if the new head reaches the food, keep the tail (snake grows), add score, and shorten the tick interval.
5. **Collision** — wall or self contact ends the game and shows the final score.

Input from keyboard, touch swipe, and buttons all funnel into one `setDir()` function, which also blocks 180° turns so you can't reverse into yourself.

## 📁 Project structure

```
snake-game/
├── index.html   # the entire game: markup + styles + logic in one file
└── README.md
```

## 🚀 Run locally (optional)

No tooling needed — but if you prefer serving it:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## 📝 What I learned

- Modeling a game as grid coordinates and a timed update loop
- Translating between grid space and canvas pixel space for rendering
- Unifying keyboard, touch, and button input behind one control function
- Using `localStorage` for lightweight persistence
- Building and iterating with an AI pair-programmer ("vibe coding"): specifying behavior in plain language, play-testing, and fixing issues one at a time

## 📄 License

MIT — feel free to fork and remix.
