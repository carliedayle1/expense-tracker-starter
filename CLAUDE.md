# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Expense tracker starter project from the [Claude Code course](https://codewithmosh.com/p/claude-code). A single-page React app for tracking income and expenses. Intentionally ships with bugs, poor UI, and messy code to be improved during the course.

## Commands

- `npm run dev` — Start Vite dev server (http://localhost:5173)
- `npm run build` — Production build to `dist/`
- `npm run lint` — ESLint check
- `npm run preview` — Preview production build

## Architecture

Single-component React app (Vite + React 19, JSX, no TypeScript). All application logic lives in `src/App.jsx` — state management, form handling, filtering, and rendering are in one file with no component extraction.

## Known Issues

- Transaction amounts are stored as strings, causing string concatenation instead of numeric addition in balance calculations.
- "Freelance Work" is categorized as "expense" instead of "income" in seed data.
