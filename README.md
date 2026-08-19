# meeting-scheduling-platform
A web-based meeting scheduling platform

# MeetSchedule

A web-based meeting scheduling platform that combines **1-on-1 booking pages** and **group availability polling** into a single product — something no existing tool currently does well.

> Built by the MICUOK dev team as a full-stack portfolio project.

---

## ✨ What It Does

- **Book 1-on-1 meetings** via a shareable link — no back-and-forth emails
- **Poll a group for availability** and auto-confirm the winning slot
- **Syncs with Google, Outlook & iCal** calendars
- **Auto-detects timezones** so everyone sees their local time
- **Sends reminders** so nobody forgets

---

## 🗂️ Repository Structure

```
meetschedule/
├── apps/
│   ├── web/          # Next.js 14 frontend
│   └── api/          # Node.js + Hono backend
├── packages/
│   ├── ui/           # Shared component library (shadcn/ui)
│   └── types/        # Shared TypeScript types
├── .github/
│   ├── workflows/    # GitHub Actions CI/CD
│   └── ISSUE_TEMPLATE/
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
└── README.md
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Next.js 14 (App Router) |
| Styling | Tailwind CSS + shadcn/ui |
| Backend | Node.js + Hono |
| Database | PostgreSQL + Prisma |
| Auth | Auth.js (NextAuth) |
| Email | Resend + React Email |
| Deployment | Vercel (web) + Railway (API/DB) |
| Testing | Vitest + Playwright |

---

## 🚀 Getting Started

### Prerequisites

- Node.js 20+
- pnpm 9+
- PostgreSQL 15+

### Local Setup

```bash
# 1. Clone the repo
git clone https://github.com/YOUR_ORG/meetschedule.git
cd meetschedule

# 2. Install dependencies
pnpm install

# 3. Set up environment variables
cp .env.example .env
# Fill in your values in .env

# 4. Set up the database
pnpm db:migrate

# 5. Start the dev servers
pnpm dev
```

The web app runs at `http://localhost:3000` and the API at `http://localhost:3001`.

---

## 🔑 Environment Variables

Copy `.env.example` to `.env` and fill in the values. Never commit your real `.env` file.

| Variable | Description |
|---|---|
| `DATABASE_URL` | PostgreSQL connection string |
| `NEXTAUTH_SECRET` | Random secret for Auth.js |
| `GOOGLE_CLIENT_ID` | Google OAuth app ID |
| `GOOGLE_CLIENT_SECRET` | Google OAuth secret |
| `RESEND_API_KEY` | Resend email API key |

---

## 🧪 Running Tests

```bash
# Unit + integration tests
pnpm test

# End-to-end tests
pnpm test:e2e

# Type checking
pnpm typecheck

# Linting
pnpm lint
```

---

## 📖 Documentation

| Doc | Description |
|---|---|
| [CONTRIBUTING.md](./CONTRIBUTING.md) | How to contribute — branching, PRs, commit style |
| [CODE_OF_CONDUCT.md](./CODE_OF_CONDUCT.md) | Team conduct expectations |
| [Confluence Space](https://YOUR_CONFLUENCE_URL) | Research docs, meeting notes, decisions |

---

## 👥 Team

Built by the MICUOK dev team. To add a new team member, see [CONTRIBUTING.md](./CONTRIBUTING.md).

---

## 📄 License

MIT
