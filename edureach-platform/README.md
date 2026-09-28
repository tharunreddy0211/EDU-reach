# EduReach — Agentic College Chatbot · Part 1 starter

Starter code for **Part 1: Project Setup and JWT Authentication**.

Download this, then follow the Part 1 reading material. Everything the material hands you
as a *"provided file"* is already here, so you never type a config file. Everything the
material asks you to **Build** is yours to write.

> Part 1 is published as **two reading materials** — a backend document (Backend Steps 1–10)
> followed by a frontend document (Frontend Steps 1–9). Work through them in that order.

## Already provided

| | |
|---|---|
| `server/` | `package.json` (all dependencies, incl. the LangChain packages Part 2 needs), `tsconfig.json`, `.env.example` |
| `client/` | `package.json`, `vite.config.ts`, 3× `tsconfig`, `eslint.config.js`, `index.html`, `src/index.css`, `src/main.tsx` |

The folder structure under `server/src/` and `client/src/` is created and empty — each
folder is where its step tells you to add files.

`client/src/App.tsx` is a placeholder so `npm run dev` boots right away. You replace it in
the last frontend step, *"Wire Up the App Router"*.

## You will build

**Backend** — *Build the Database Connection* → *Build Express App and Server* (Steps 3–10):
`database.config.ts`, `user.model.ts`, `password.util.ts`, `jwt.util.ts`,
`auth.middleware.ts`, `auth.controller.ts`, `auth.routes.ts`,
`error-handler.middleware.ts`, `app.ts`, `server.ts`

**Frontend** — *Build the API Service Layer* → *Wire Up the App Router* (Steps 2–9):
`api.ts`, `auth.service.ts`, `AuthContext.tsx`, `LoginPage.tsx`, `SignupPage.tsx`,
`content.ts`, all 14 components, `HomePage.tsx`, `App.tsx`

## First-time setup

```bash
# 1. Backend
cd server
npm install
cp .env.example .env      # then fill in your own values
```

```bash
# 2. Frontend (second terminal)
cd client
npm install
npm run dev               # http://localhost:5173
```

`server/src` is empty until you start building, so `npm run dev` and `npm run build` in
`server` only work once you reach *"Build Express App and Server"*.

### Environment variables

Copy `server/.env.example` to `server/.env` and fill in:

| Variable | Where to get it |
|---|---|
| `MONGODB_URI` | MongoDB Atlas → Connect → Drivers (Backend Step 1) |
| `JWT_SECRET` | Any long random string you choose |

Requires **Node.js 24+** — the server runs `.ts` files directly, with no build step.

> `.env` is gitignored. Never commit real credentials.

## Session goal

Sign up a new user, land on the homepage logged in, and see the Student Life / Events /
Counselor / Hiring Stats sections appear only when logged in — and disappear on logout.
