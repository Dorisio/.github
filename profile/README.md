# TipForge Organization

Welcome to **TipForge** — Creator Tipping Infrastructure built on Stellar blockchain.

## 🎯 Mission

Enable creators worldwide to receive instant USDC payments from fans across any platform, removing payment friction and geographic barriers.

## 📦 Repositories

TipForge is organized as three independent, tightly-integrated repositories:

### 1. [Backend](https://github.com/TipForge/backend-)

**Core system of intelligence and infrastructure**

- REST API for all operations
- User authentication and creator management
- Payment orchestration and Stellar integration
- PostgreSQL database + Redis caching
- Source of truth for all business rules

**Tech:** Fastify, Node.js, TypeScript, PostgreSQL, Redis, Stellar SDK

---

### 2. [SDK](https://github.com/TipForge/sdk)

**Clean abstraction layer for developers**

- Type-safe client library wrapping backend APIs
- Framework-agnostic core (works with any JavaScript framework)
- Optional React hooks for seamless integration
- Utility functions for wallet, transaction, validation operations
- Npm package for easy integration into third-party apps

**Tech:** TypeScript, Stellar SDK, Zod, React (optional)

---

### 3. [Frontend](https://github.com/TipForge/frontend)

**User-facing web application**

- Landing page and user onboarding
- Creator profile pages and dashboards
- Send tip flow (minimal UI, maximum simplicity)
- Creator earnings dashboard
- Responsive design with Tailwind CSS

**Tech:** Next.js, React, TypeScript, Tailwind CSS, Framer Motion, TanStack Query

---

## 🏗️ Architecture

```
Frontend (Next.js)
    ↓
SDK (TypeScript abstraction)
    ↓
Backend (Fastify)
    ↓
Stellar Blockchain
```

## 🚀 Quick Start

### Clone all repos

```bash
git clone https://github.com/TipForge/backend-.git backend
git clone https://github.com/TipForge/sdk.git sdk
git clone https://github.com/TipForge/frontend.git frontend
```

### Install dependencies

```bash
cd backend && npm install
cd ../sdk && npm install
cd ../frontend && npm install
```

### Setup backend database

```bash
cd backend
npm run prisma:generate
npm run prisma:migrate
```

### Start development

```bash
# Terminal 1: Backend
cd backend && npm run dev

# Terminal 2: SDK
cd sdk && npm run build --watch

# Terminal 3: Frontend
cd frontend && npm run dev
```

## 📋 Prerequisites

- **Node.js** 20+ LTS
- **PostgreSQL** 14+
- **Redis** 6+

## 🔧 Key Design Principles

### Contract-First Development

- Backend defines API contracts first
- SDK wraps those contracts
- Frontend consumes stabilized SDK

### Separation of Concerns

- **Backend** = All logic, auth, payments, business rules
- **SDK** = Translation layer, validation helpers, utilities
- **Frontend** = Experience only, calls SDK, zero business logic

### Repo Independence

- Each repo builds, tests, deploys independently
- No hidden cross-repo coupling at runtime

## 📚 Documentation

Each repo has comprehensive documentation:

- **Backend:** [backend/README.md](https://github.com/TipForge/backend-) — API contracts, database schema, development guide
- **SDK:** [sdk/README.md](https://github.com/TipForge/sdk) — API reference, usage examples, React hooks
- **Frontend:** [frontend/README.md](https://github.com/TipForge/frontend) — Component structure, state management

## 🛠️ Code Standards

All repos follow these standards:

- **TypeScript:** Strict mode enabled
- **Formatting:** Prettier (100 char line width)
- **Linting:** ESLint with TypeScript plugin
- **Testing:** Vitest for unit/integration tests
- **Validation:** Zod schemas for runtime type safety

## 🌟 Key Features

- ✅ Instant USDC payments via Stellar
- ✅ Multi-platform creator profiles (X, Instagram, TikTok, YouTube, GitHub, Twitch)
- ✅ No geographic barriers or regional restrictions
- ✅ Low transaction fees powered by Stellar
- ✅ Simple onboarding for creators and fans
- ✅ Creator dashboard with earnings tracking
- ✅ Developer-friendly SDK for integrations
- ✅ Type-safe TypeScript throughout

---

**Built with ❤️ by the TipForge team**

Join us in making creator support frictionless, global, and accessible.
