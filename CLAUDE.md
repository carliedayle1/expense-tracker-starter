# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Expense tracker starter project from the [Claude Code course](https://codewithmosh.com/p/claude-code). A single-page React app for tracking income and expenses.

## Commands

- `npm run dev` — Start Vite dev server (http://localhost:5173)
- `npm run build` — Production build to `dist/`
- `npm run lint` — ESLint check
- `npm run preview` — Preview production build

## Architecture

React 19 + Vite, JSX, no TypeScript. Components:

- `App.jsx` — Root component, owns `transactions` state and `darkMode` theme state. Passes data down to children.
- `Summary.jsx` — Computes and displays total income, expenses, and balance from `transactions` prop.
- `TransactionForm.jsx` — Form with local state for adding transactions. Calls `onAddTransaction` callback.
- `TransactionList.jsx` — Filters and displays transactions in a table. Owns filter state locally.

Categories are defined independently in `TransactionForm` and `TransactionList`.

## Styling

CSS custom properties (variables) are defined in `index.css` for theming. All component styles in `App.css` reference these variables. Dark mode is controlled via a `data-theme` attribute on `<html>`:

- Light/dark theme tokens: `--color-bg`, `--color-surface`, `--color-text`, `--color-border`, `--color-primary`, `--color-income`, `--color-expense`, etc.
- Theme preference persisted in `localStorage('theme')` and falls back to `prefers-color-scheme`.
- FOUC prevention: inline `<script>` in `index.html` sets `data-theme` before React loads.

## Known Issues

- "Freelance Work" is categorized as "expense" instead of "income" in seed data.
