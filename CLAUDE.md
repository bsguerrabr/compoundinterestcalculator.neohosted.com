# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

Compound Interest Calculator - a single-page static web application hosted on Cloudflare Pages via neohosted.com.

## Tech Stack

- Vanilla HTML/CSS/JavaScript (no build step required)
- Chart.js (CDN) for interactive line charts

## Development

Open `index.html` directly in a browser, or use a local server:
```bash
npx serve .
# or
python -m http.server 8000
```

## Deployment

Static site - deploy to Cloudflare Pages by connecting the Git repo or drag-and-drop files.

## Architecture

- `index.html` - Page structure with form inputs and chart container
- `styles.css` - Responsive layout (form left, chart right on desktop; stacked on mobile)
- `script.js` - Calculator logic and Chart.js integration with real-time updates

### Calculator Logic

Compound interest formula with monthly contributions:
```
For each month: accumulated = previous * (1 + monthlyRate) + monthlyContribution
```
- Converts annual rate to monthly using: `(1 + annualRate)^(1/12) - 1`
- Chart displays 3 lines: Accumulated Total, Total Invested, Total Interest
