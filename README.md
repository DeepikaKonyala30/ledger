# 💹 SmartLedger

> **Your finances, finally under control — without the spreadsheets.**

Most people don't know where their money goes. SmartLedger fixes that — not with manual entry or dashboards you have to interpret yourself, but with an AI that understands your finances and tells you exactly what to do about them.

Ask it anything in plain English. It scans your bills, reads your bank SMSes, tracks your investments, flags anomalies, and recommends tax-saving moves before you miss the window. All of it — on web and mobile.


## 😩 The Problem

Every personal finance tool puts the burden on *you*.

Categorize this transaction. Build this report. Remember to log that expense. Set this budget manually. Most people abandon these tools in two weeks — not because they don't care about money, but because the tool feels like a second job.

**SmartLedger flips the model.** Connect your data once, and the AI does the heavy lifting. It surfaces insights you wouldn't have noticed, warns you before you overspend, and acts like a CFO sitting right in your pocket.


## ✨ Features

### 🤖 AI Financial Advisor
*Talk to your money like you'd talk to a person.*

Ask — "where did most of my money go last month?", "am I on track for my savings goal?", "what can I do to pay less tax this year?" — and get real, grounded answers based on your actual data. Not generic advice. Not a pie chart. A direct answer with next steps.

### 📸 Smart Expense Tracking
*Zero manual entry. Seriously.*

Point your camera at a bill and it's logged. Bank SMS alerts are parsed automatically. Unusual charges are flagged the moment they appear. Expenses are categorized, enriched, and ready for analysis before you even open the app.

### 🧾 Tax Optimization Engine
*Stop leaving money on the table.*

SmartLedger maps your eligible deductions, simulates different tax scenarios, and recommends ELSS, PPF, and NPS allocations — proactively, before the financial year closes and the window is gone.

### 📈 Investment Command Center
*Know what you have. Know what to do with it.*

Live portfolio view across all instruments. AI-driven allocation suggestions. Real-time market context via Yahoo Finance. You're not just tracking numbers — you're getting told what moves to make.

### 👨‍👩‍👧 Family Finance System
*Everyone on the same page, finally.*

Role-based accounts for every member. Shared budgets. A single collaborative dashboard so the whole household is working from the same picture — no more "I thought you tracked that."

### 🎮 Gamification & Wellness
*Good habits, made rewarding.*

Streaks, XP, missions, badges, and a financial health score that turns boring financial discipline into something you actually want to keep up with.


## ⚙️ How It Works

SmartLedger runs four specialized AI agents — **Advisor**, **Tax**, **Investment**, and **Wellness** — that collaborate behind every query. Each agent is grounded in your real data via a RAG pipeline, so every response is specific to *you*, not recycled financial wisdom.

Every decision the AI makes is written to a tamper-proof audit log. Full transparency, always.

```
Your data → Ingestion → Enrichment → Agent Reasoning → Response + Audit Log
```


## 🛠️ Tech Stack

### Backend
- ⚡ Node.js 20, Express.js
- 🍃 MongoDB with Mongoose
- 🔐 JWT authentication + Google OAuth
- 🤖 Gemini AI SDK (text + vision), Yahoo Finance
- 🕐 Cron jobs, Winston logging

### Web Frontend
- ⚛️ React 18, Vite, Tailwind CSS
- 🗂️ Zustand for state management
- 📊 Recharts for data visualization
- 🎞️ Framer Motion, Lucide React

### Mobile (Expo / React Native)
- 📱 React Navigation, AsyncStorage
- 💬 SMS listener and parser
- 🔔 Expo Notifications
- 📉 React Native Chart Kit


## 📂 Project Structure

```
SmartLedger/
├── backend/
│   ├── controllers/       # Route handlers
│   ├── routes/            # API route definitions
│   ├── services/          # Business logic & AI agent orchestration
│   ├── models/            # Mongoose schemas
│   └── middleware/        # Auth, logging, error handling
├── frontend/
│   ├── src/
│   │   ├── components/    # Reusable UI components
│   │   ├── pages/         # Route-level views
│   │   ├── stores/        # Zustand state stores
│   │   └── hooks/         # Custom React hooks
└── frontend_app/
    └── src/
        ├── screens/       # Mobile screen components
        ├── navigation/    # Stack and tab navigators
        ├── api/           # Axios config and endpoints
        └── parsers/       # SMS parsing utilities
```


## 🚀 Getting Started

**Prerequisites:** Node.js 20+, MongoDB (local or Atlas), a [Gemini API key](https://ai.google.dev/), and Expo CLI for mobile.

```bash
git clone https://github.com/your-username/SmartLedger.git

cd backend && npm install
cd ../frontend && npm install
cd ../frontend_app && npm install
```

### 🔑 Environment Variables

**`backend/.env`**

| Variable | Description | Required |
|---|---|---|
| `MONGO_URI` | MongoDB connection string | ✅ |
| `JWT_SECRET` | Secret for signing JWTs | ✅ |
| `GEMINI_API_KEY` | Google Gemini API key | ✅ |
| `GOOGLE_CLIENT_ID` | Google OAuth client ID | Optional |
| `GOOGLE_CLIENT_SECRET` | Google OAuth client secret | Optional |
| `PORT` | Server port (default: 5000) | Optional |

**`frontend/.env`**

```
VITE_BACKEND_URL=http://localhost:5000
```

> 📌 In `frontend_app/src/api/config.js`, use your machine's **LAN IP** instead of `localhost` — physical devices can't resolve localhost over the network.

### ▶️ Run

```bash
cd backend && npm run dev        # API  →  localhost:5000
cd frontend && npm run dev       # Web  →  localhost:5173
cd frontend_app && npm start     # Mobile  →  Expo QR
```


## 📡 API Reference

All routes are prefixed with `/api/v1`.

| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/auth/register` | Register a new user |
| `POST` | `/auth/login` | Login and receive JWT |
| `GET` | `/expenses` | Fetch paginated expenses |
| `POST` | `/expenses` | Add a new expense |
| `POST` | `/expenses/scan` | Upload bill image for AI parsing |
| `GET` | `/budget` | Fetch current budget |
| `GET` | `/investments/portfolio` | Portfolio summary |
| `GET` | `/tax/suggestions` | AI-generated tax deduction tips |
| `POST` | `/ai/query` | Natural language financial query |
| `GET` | `/wellness/score` | Gamification stats and health score |


## 🌟 The Vision

SmartLedger isn't just an app — it's a step toward a world where financial clarity isn't a privilege reserved for people who can afford advisors or have hours to spend on spreadsheets.

Everyone deserves to know where their money is going, what they can do about it, and how to build something better for themselves and their families.

That's what we're building.


<div align="center">

**Built with purpose. Powered by AI. Designed for real life.**

*If SmartLedger resonates with you — star the repo, share it, or just use it. That's enough.* ⭐

</div>


## 💬 Finally

Most finance apps show you data. SmartLedger tells you what to do with it.

Clone it, run it, break it, improve it — and for the first time, actually know where your money is going.
