# SmartLedger

SmartLedger is a personal finance project I built as a full-stack learning/hackathon style application. The main idea is to bring expense tracking, budgets, investments, tax helpers, family finance, SMS parsing, and an AI chat flow into one app instead of keeping them as separate demos.

This repository currently has three parts:

- `backend/` - Express and MongoDB API
- `frontend/` - React + Vite web app
- `frontend_app/` - Expo / React Native mobile app

I have kept this README practical on purpose. It describes what is present in the codebase, not what the project could become later.

## What It Does

The app includes code for:

- User signup, login, JWT auth, Google OAuth routes, and password reset flow
- Expense and transaction tracking
- Budget creation and budget-vs-expense comparison
- Dashboard and analytics views
- Bill scanning flow using Gemini helpers
- SMS transaction parsing in the mobile app
- Investment tracking screens and backend services
- AI analysis, AI investment planning, and an agent chat interface
- Tax optimizer screens and backend tax calculation/recommendation services
- Family finance features such as family groups, members, shared budgets, and notifications
- Gamification features such as XP, levels, missions, badges, streaks, and wellness score
- Recurring expense processing with scheduled jobs
- Settings screens for profile, notifications, family, tax, AI, and app preferences

Some of these features depend on environment variables and external APIs, so they may need setup before they work end-to-end on a new machine.

## Tech Stack

### Backend

- Node.js
- Express
- MongoDB with Mongoose
- JWT authentication
- Passport Google OAuth
- Nodemailer
- Google Generative AI SDK
- Multer
- Node cron
- Winston and Morgan logging
- Joi validation
- Axios
- Yahoo Finance and RSS parser utilities

### Web Frontend

- React
- Vite
- React Router
- Tailwind CSS
- Axios
- Recharts
- Zustand
- Framer Motion
- Lucide React
- Three.js / React Three Fiber

### Mobile App

- Expo
- React Native
- React Navigation
- Axios
- AsyncStorage
- Expo notifications
- Expo local credential storage package
- React Native SMS listener / SMS reader packages
- React Native chart kit
- Zustand

## Project Structure

```text
SmartLedger/
  backend/
    controllers/       Express controller logic
    middleware/        Auth, validation, rate limit, and request helpers
    models/            Mongoose models
    routes/            API routes
    services/          Finance, tax, investment, gamification, and family services
    utils/             AI helpers, parsers, market data helpers, cron helpers
    server.js          Backend entry point

  frontend/
    src/
      components/      Web UI components
      context/         React context providers
      pages/           Web app pages
      services/        API service wrappers
      store/           Zustand stores
      utils/           Shared frontend utilities

  frontend_app/
    src/
      api/             Mobile API client and backend URL config
      components/      Mobile UI components
      context/         Mobile auth/finance/family providers
      navigation/      React Navigation setup
      screens/         Mobile app screens
      store/           Mobile Zustand stores
      utils/           SMS parser, risk engine, notifications, formatters
```

## Getting Started

### 1. Install dependencies

Backend:

```bash
cd backend
npm install
```

Web frontend:

```bash
cd frontend
npm install
```

Mobile app:

```bash
cd frontend_app
npm install
```

### 2. Configure environment variables

Create a `.env` file in `backend/`.

```env
PORT=5000
MONGO_URI=mongodb://127.0.0.1:27017/smartledger
JWT_SECRET=replace_this_with_a_local_secret
FRONTEND_URL=http://localhost:5173
FRONTEND_URL_APP=http://localhost:8081

# Optional, needed for related features
GOOGLE_CLIENT_ID=
GOOGLE_CLIENT_SECRET=
EMAIL_USER=
EMAIL_PASS=
GEMINI_API_KEY=
```

Create a `.env` file in `frontend/`.

```env
VITE_BACKEND_URL=http://localhost:5000
```

For the mobile app, update the local IP in:

```text
frontend_app/src/api/config.js
```

That file is currently used to decide which backend URL the Expo app should call during development.

### 3. Run the backend

```bash
cd backend
npm run dev
```

The backend defaults to:

```text
http://localhost:5000
```

### 4. Run the web app

```bash
cd frontend
npm run dev
```

Vite usually opens the web app at:

```text
http://localhost:5173
```

### 5. Run the mobile app

```bash
cd frontend_app
npm start
```

Then use the Expo options for Android, iOS, or web depending on your setup.

## Main Backend Routes

The backend registers these route groups in `backend/server.js`:

- `/api/auth`
- `/api/transactions`
- `/api/budgets`
- `/api/dashboard`
- `/api/billscan`
- `/api/investments`
- `/api/investments/ai`
- `/api/ai-analysis`
- `/api/budget-comparison`
- `/api/notifications`
- `/api/users`
- `/api/gamification`
- `/api/financial`
- `/api/recurring`
- `/api/family`
- `/api/family-budget`
- `/api/tax`
- `/api/settings`
- `/api/agent`
- `/api/sms`

Most routes after auth use the auth middleware, so a valid token is expected.

## Notes

- This is a student project, so some parts are more polished than others.
- There is no real test suite yet. The backend `npm test` script is still a placeholder.
- Some files contain hosting config such as `vercel.json`, but this README does not assume a hosted version is active.
- AI, email, OAuth, and market-data related flows need valid keys or credentials.
- The mobile SMS features depend on platform permissions and device behavior, so they should be tested on the target device setup.

## Why I Built It

I wanted to practice building a finance-focused product that goes beyond a simple CRUD expense tracker. SmartLedger became a way to combine API design, React dashboards, mobile screens, MongoDB models, background jobs, AI helpers, and personal finance workflows in one project.

The project is useful for demonstrating full-stack application structure, feature integration, and the kind of product thinking expected in hackathons or internship projects.
