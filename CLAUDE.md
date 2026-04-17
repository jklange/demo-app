# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A single-file static web app (`index.html`) — no build step, no package manager, no framework. Open directly in a browser.

## Architecture

Everything lives in `index.html`:
- **Styles** — CSS custom properties for theming, component-scoped rules
- **HTML** — card-based grid layout, one card per widget
- **JavaScript** — vanilla JS at the bottom; each widget is self-contained with its own functions and state

### Widgets
- **Live Clock** — `updateClock()`, runs on 1s interval
- **Counters (1–3)** — shared `counts` object keyed by id, `adjustCounter(id, delta)` / `resetCounter(id)`
- **Todo List** — persisted to `localStorage` under `demo-todos`, rendered via `renderTodos()`
- **Color Mixer** — HSL sliders → hex badge via a 1×1 canvas, `updateColor()`
- **Quick Note** — debounced `localStorage` save under `demo-note`
- **Activity Chart** — random bar data, re-rendered on click or `randomizeChart()`

## Git Workflow

After any change: commit with a descriptive message and push so GitHub stays current.

```bash
git add .
git commit -m "description of change"
git push
```
