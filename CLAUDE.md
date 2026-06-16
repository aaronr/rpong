# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## About

A browser-based Pong game served via GitHub Pages at [aaronr.github.io/rpong](https://aaronr.github.io/rpong/). No build system — the entire game is a single `index.html` file.

## Commands

```bash
# Serve locally
python -m http.server
```

## Deployment

Any push to `main` auto-deploys to GitHub Pages. No manual steps required.

## Architecture

All game logic, rendering, and styles live in `index.html`. The game runs on an HTML5 `<canvas>` using `requestAnimationFrame`.

**Coordinate system:** All game positions are in logical units (`W=900`, `H=600`). The `s(v)` function scales any logical value to canvas pixels at draw time, keeping the layout responsive as the canvas resizes to fit the viewport.

**Game state:** A single `state` object holds scores, paddle positions (`state.left`, `state.right`), and ball (`state.ball` with `x`, `y`, `vx`, `vy`).

**Left paddle** is always AI — tracks the ball's `y` position each frame with a capped speed (4.2 units/frame) so it can be beaten.

**Right paddle** is always the human player, controlled by `↑`/`↓` arrow keys. Touch drag on the canvas also moves the right paddle.

**Ball deflection:** Angle off a paddle is determined by where the ball hits relative to the paddle center (±60°), plus a small random jitter (±6°) to prevent perfectly predictable returns. Speed increases 5% per hit, capped at 14 units/frame.

**Controls:**
- `↑` / `↓` — move player paddle
- `Space` / `Enter` — start or serve next point
- `Esc` — reset game to initial state
