# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

FERRO is a single-page static website for a brand strategy / cultural consulting agency. The entire site lives in one file: `FERRO Website.html` (embedded CSS + JS, no build step).

## Running Locally

Open the file directly in a browser:
```bash
open "FERRO Website.html"
```

No server, bundler, or dependencies required.

## Architecture

Single file structure:
- **`<style>` block** — all CSS, organized as: reset → layout (`.container`, `.nav`) → section color themes (`.section.red`, `.section.pink`, `.section.light`, `.section.dark`, `.section.white`) → typography → component styles (`.tag`, `.code-item`, `.client-logo`) → animations → responsive breakpoints
- **`<body>`** — sequential `<section class="section [theme]">` blocks: Hero → Problem → Approach → Symbolic Code → Foresight Model → Services → Contact
- **JavaScript** (inline at bottom) — IntersectionObserver for scroll-triggered `.animate-in` / `.visible` classes; header background swaps on section scroll

## Key Conventions

- Section color themes are set via a single class on `<section>`: `red`, `pink`, `light`, `dark`, or `white`. All child element color overrides live under that theme class in the CSS.
- Animation staggering uses `.stagger-1` through `.stagger-6` utility classes (each adds `0.1s` transition-delay).
- Typography uses `clamp()` for fluid sizing — edit the `clamp(min, preferred, max)` values to adjust scale.
- Colors: brand blue `#2c5aa0`, red `#d63031`, pink `#fd79a8`, yellow `#ffeaa7`, dark `#2d3436`.
