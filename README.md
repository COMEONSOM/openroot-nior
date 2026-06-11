<div align="center">

  <h1>Openroot NIOR</h1>
  <p><strong>India's Indigenous AI-Powered Tool Hub</strong></p>
  <p>Built by <a href="https://openroot.in/">Openroot Systems</a></p>

  <p>
    <img src="https://img.shields.io/badge/React-19-61DAFB?style=for-the-badge&logo=react&logoColor=black" alt="React">
    <img src="https://img.shields.io/badge/TypeScript-5-3178C6?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript">
    <img src="https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white" alt="Vite">
    <img src="https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=black" alt="Firebase">
  </p>

  <p>
    <img src="https://img.shields.io/badge/Chart.js-FF6384?style=for-the-badge&logo=chartdotjs&logoColor=white" alt="Chart.js">
    <img src="https://img.shields.io/badge/Gemini_AI-4285F4?style=for-the-badge&logo=google&logoColor=white" alt="Gemini">
    <img src="https://img.shields.io/badge/localStorage-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="localStorage">
  </p>

</div>

---

## Table of Contents

- [Overview](#overview)
- [Architecture](#architecture)
- [Technology Stack](#technology-stack)
- [Available Tools](#available-tools)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Environment Variables](#environment-variables)
- [Firebase Setup](#firebase-setup)
- [UI / UX Notes](#ui--ux-notes)
- [Implementation Notes](#implementation-notes)
- [Suggested Improvements](#suggested-improvements)

---

## Overview

**Openroot NIOR** is a modular React application built with TypeScript and Vite. It combines practical financial calculators with playful interactive tools under a unified premium dark interface.

> **Product Name:** Openroot NIOR
> **Organization:** Openroot Systems
> **Type:** React + Vite single-page application

The project is organized as a **tool hub** with two primary categories:

- **Financial Engines** — serious calculators for gold, stocks, SIP, and credit/EMI planning
- **Fun Zone** — light AI-inspired experiences including a love calculator and tarot reading

---

## Architecture

```
+------------------------------------------------+
|              Openroot NIOR (SPA)               |  <- React 19 + TypeScript + Vite
|                                                |
|  +------------------+  +-----------------+     |
|  | Financial Engines|  |    Fun Zone     |     |
|  |                  |  |                 |     |
|  | +------------+   |  | +-----------+   |     |
|  | | Midas      |   |  | | Loveria   |   |     |
|  | | InvestIQ   |   |  | | Doze      |   |     |
|  | | MoneyGrow  |   |  | +-----------+   |     |
|  | | Debt Decoder   |  | +-----------+   |     |
|  | +------------+   |  | | LoveTarot |   |     |
|  +------------------+  | +-----------+   |     |
|                        +-----------------+     |
|                                                |
|  +------------------------------------------+  |
|  |         App.tsx — Category & Tool Router |  |
|  +------------------------------------------+  |
|  |     localStorage — Session Persistence   |  |
|  +------------------------------------------+  |
|  |    Firebase Hosting — Static Delivery    |  |
+------------------------------------------------+
```

### Core Components

| Component | Role | Description |
|-----------|------|-------------|
| **App.tsx** | Application Shell | Controls category switching, tool selection, sidebar and mobile layout |
| **Financial Engines** | Calculator Tools | Gold pricing, stock averaging, SIP growth, EMI and credit planning |
| **Fun Zone** | Interactive Experiences | Love-score calculator with Gemini AI, tarot-inspired numerology |
| **Firebase Hosting** | Deployment Layer | Serves the production `dist/` folder with SPA rewrite rules |
| **localStorage** | State Persistence | Restores the last-used category and tool on page load |

---

## Technology Stack

| Layer | Technology | Purpose |
|-------|------------|---------|
| Frontend Framework | React 19 | Component-based UI architecture |
| Language | TypeScript | Type-safe development |
| Build Tool | Vite | Fast dev server and optimized production builds |
| Styling | Custom CSS | Premium dark visual system via `global.css` |
| Charts | Chart.js | Financial data visualization |
| AI Integration | `@google/generative-ai`, `@google/genai` | Gemini-powered responses in Loveria Doze |
| Hosting | Firebase Hosting | SPA-optimized static delivery |
| State Persistence | `localStorage` | Last-session restore across page reloads |

---

## Available Tools

### Financial Engines

| Tool | Description |
|------|-------------|
| **Midas Engine** | Gold cost estimation and pricing flow |
| **InvestIQ Engine** | Stock average / trade averaging calculator |
| **MoneyGrow Engine** | SIP and lump-sum investment growth estimator |
| **Debt Decoder Engine** | Credit and EMI planning with Chart.js visualization |

### Fun Zone

| Tool | Description |
|------|-------------|
| **Loveria Doze** | Love-score style chat experience powered by Google Gemini |
| **Tarot Reading** | Numerology-style compatibility and tarot-inspired results |

---

## Project Structure

```text
openroot-nior/
├── public/
│   └── assets/
│       ├── company-icon.avif
│       ├── openroot-white-nobg.png
│       └── icons/
│           ├── calculator.png
│           ├── credit-card.png
│           ├── gold-bars.png
│           ├── growth-graph.png
│           ├── love.png
│           └── tarrot.jpg
├── src/
│   ├── App.tsx                  # Application shell — category and tool routing
│   ├── main.tsx                 # React entry point
│   ├── global.css               # Theme system and responsive layout rules
│   ├── global.d.ts              # Global TypeScript declarations
│   ├── lib/
│   │   └── firebase.ts          # Firebase initialization
│   └── tools/
│       ├── models/              # Financial calculator components
│       │   ├── gold.tsx         # Midas Engine
│       │   ├── stockavg.tsx     # InvestIQ Engine
│       │   ├── sip.tsx          # MoneyGrow Engine
│       │   └── credit.tsx       # Debt Decoder Engine
│       └── fun/                 # Interactive experience components
│           ├── LoveCalculator.tsx  # Loveria Doze
│           └── LoveTarot.tsx       # Tarot Reading
├── firebase.json                # Firebase Hosting config with SPA rewrite rules
├── vite.config.ts
├── tsconfig.json
└── package.json
```

---

## Getting Started

### Prerequisites

- Node.js (LTS recommended)
- npm
- Firebase CLI (only required for deployment)

### Quick Start

```bash
# 1. Install dependencies
npm install

# 2. Start the development server
npm run dev

# 3. Build for production
npm run build

# 4. Preview the production build locally
npm run preview

# 5. Lint the codebase
npm run lint
```

### Development Server

| Mode | Command | Output |
|------|---------|--------|
| Development | `npm run dev` | Local Vite dev server with HMR |
| Production Build | `npm run build` | Optimized output in `dist/` |
| Production Preview | `npm run preview` | Serves `dist/` locally for verification |

---

## Environment Variables

The **Loveria Doze** tool uses the Google Gemini API when a key is present. The app runs without it — the AI-driven feature falls back gracefully when the key is missing.

Create a `.env` file in the project root:

```env
VITE_GEMINI_KEY=your_gemini_api_key_here
```

> **Note:** All Vite environment variables exposed to the frontend must be prefixed with `VITE_`. Never commit `.env` to version control.

---

## Firebase Setup

Firebase Hosting is pre-configured for a single-page application in `firebase.json`. All routes are rewritten to `index.html` so React Router handles client-side navigation correctly.

### Deploy to Firebase

```bash
# Authenticate with Firebase
firebase login

# Initialize hosting (first time only)
firebase init hosting

# Build and deploy
npm run build
firebase deploy
```

### Deployment Checklist

- [ ] Run `npm run build` and verify `dist/` is generated
- [ ] Confirm `firebase.json` rewrites point all routes to `index.html`
- [ ] Run `firebase deploy`
- [ ] Verify the live URL loads correctly and the last-session restore works

---

## UI / UX Notes

- The application uses a **premium dark visual language** throughout
- The sidebar layout adapts into a **mobile-first top shell** for smaller screens
- The selected tool and category are restored from `localStorage` on every page load
- All static assets are loaded from `/public/assets`
- The tool layout is designed for fast switching between financial and fun modules

---

## Implementation Notes

| File | Responsibility |
|------|----------------|
| `src/App.tsx` | Controls category switching and active tool selection |
| `src/global.css` | Defines the theme system, CSS variables, and responsive layout |
| `src/lib/firebase.ts` | Initializes the Firebase app instance |
| `src/tools/models/` | Contains all financial calculator components |
| `src/tools/fun/` | Contains all interactive fun experience components |

---

## Suggested Improvements

These additions would strengthen the project in future iterations:

- Add a dedicated **home dashboard** with tool descriptions and quick-access cards
- Move sensitive Firebase configuration values into environment variables
- Add consistent **loading, error, and empty states** across all tools
- Standardize asset and component file naming conventions
- Add automated unit tests for calculator logic and form validation flows

---

<div align="center">

**Maintained by [Openroot Systems](https://openroot.in/)**

<p>
  <img src="https://img.shields.io/badge/Made%20with-React_19-61DAFB?style=flat-square&logo=react&logoColor=black" alt="React">
  <img src="https://img.shields.io/badge/License-Proprietary-red?style=flat-square" alt="License">
</p>

</div>
