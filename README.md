# rpong

A browser-based Pong game running on [GitHub Pages](https://aaronr.github.io/rpong/).

## About

This is a small experiment using [Claude Code](https://claude.ai/code) to generate an interactive game entirely in the browser — no frameworks, no build tools, just a single `index.html` file. The goal was to see how quickly Claude could go from an empty directory to a playable, deployed game.

The entire development session — from `mkdir rpong` to live URL — was driven through Claude Code, including writing the game logic, initializing the git repo, creating the GitHub repository, and enabling GitHub Pages.

## How to play

Visit [aaronr.github.io/rpong](https://aaronr.github.io/rpong/) in any modern browser.

- `↑` / `↓` — move your paddle (right side)
- `Space` or `Enter` — serve the next point
- `Esc` — reset the game

First to 7 points wins. The left paddle is controlled by an AI opponent.

## Running locally

```bash
python -m http.server
```

Then open `http://localhost:8000`.
