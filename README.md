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

**Get Started:**

```bash
git clone https://github.com/TipForge/backend-.git
cd backend
npm install
npm run prisma:migrate
npm run dev
```

---

### 2. [SDK](https://github.com/TipForge/sdk)

**Clean abstraction layer for developers**

- Type-safe client library wrapping backend APIs
- Framework-agnostic core (works with any JavaScript framework)
- Optional React hooks for seamless integration
- Utility functions for wallet, transaction, validation operations
- Npm package for easy integration into third-party apps

**Tech:** TypeScript, Stellar SDK, Zod, React (optional)

**Get Started:**

```bash
git clone https://github.com/TipForge/sdk.git
cd sdk
npm install
npm run build
```

---

### 3. [Frontend](https://github.com/TipForge/frontend)

**User-facing web application**

- Landing page and user onboarding
- Creator profile pages and dashboards
- Send tip flow (minimal UI, maximum simplicity)
- Creator earnings dashboard
- Responsive design with Tailwind CSS

**Tech:** Next.js, React, TypeScript, Tailwind CSS, Framer Motion, TanStack Query

**Get Started:**

```bash
git clone https://github.com/TipForge/frontend.git
cd frontend
cp .env.example .env.local
npm install
npm run dev
```

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

### Data Flow Example (Sending a Tip)

```
1. Fan clicks "Send Tip" in Frontend
2. Frontend calls SDK.createTip(creatorId, amount)
3. SDK validates input, sends request to Backend API
4. Backend validates auth, verifies creator wallet, builds Stellar transaction
5. Backend broadcasts transaction to Stellar network
6. SDK receives confirmation, returns to Frontend
7. Frontend shows success state, updates transaction history
```

## 🔧 Key Design Principles

### Contract-First Development

- Backend defines API contracts first (`src/types/index.ts`)
- SDK wraps those contracts
- Frontend consumes stabilized SDK

### Separation of Concerns

- **Backend** = All logic, auth, payments, business rules
- **SDK** = Translation layer, validation helpers, utilities
- **Frontend** = Experience only, calls SDK, zero business logic

### Repo Independence

- Each repo builds, tests, deploys independently
- No hidden cross-repo coupling at runtime
- Clear boundaries between layers

## 🚀 Quick Start (All Three Repos)

### 1. Clone all repos

```bash
git clone https://github.com/TipForge/backend-.git backend
git clone https://github.com/TipForge/sdk.git sdk
git clone https://github.com/TipForge/frontend.git frontend
```

### 2. Install dependencies

```bash
cd backend && npm install
cd ../sdk && npm install
cd ../frontend && npm install
```

### 3. Setup backend database

```bash
cd backend
npm run prisma:generate
npm run prisma:migrate
```

### 4. Start development

```bash
# Terminal 1: Backend
cd backend && npm run dev

# Terminal 2: SDK (compile)
cd sdk && npm run build --watch

# Terminal 3: Frontend
cd frontend && npm run dev
```

Backend runs on `http://localhost:3000`
Frontend runs on `http://localhost:3001` (or next available port)

## 📋 Prerequisites

- **Node.js** 20+ LTS
- **PostgreSQL** 14+
- **Redis** 6+
- **Git**

## 🔐 Environment Variables

### Backend (`backend/.env`)

```
DATABASE_URL=postgresql://user:password@localhost:5432/tipforge
REDIS_URL=redis://localhost:6379
JWT_SECRET=your-secret-key
STELLAR_NETWORK=testnet
STELLAR_SERVER_SECRET=your-stellar-account-secret
USDC_CONTRACT_ID=contract-id
```

### Frontend (`frontend/.env.local`)

```
NEXT_PUBLIC_API_URL=http://localhost:3000
```

## 📚 Documentation

Each repo has comprehensive documentation:

- **Backend:** [backend/README.md](https://github.com/TipForge/backend-) — API contracts, database schema, development guide
- **SDK:** [sdk/README.md](https://github.com/TipForge/sdk) — API reference, usage examples, React hooks
- **Frontend:** [frontend/README.md](https://github.com/TipForge/frontend) — Component structure, state management, development workflow

## 🛠️ Code Standards

All repos follow these standards:

- **TypeScript:** Strict mode enabled (`strict: true`)
- **Formatting:** Prettier (100 char line width, single quotes)
- **Linting:** ESLint with TypeScript plugin
- **Testing:** Vitest for unit/integration tests
- **Validation:** Zod schemas for runtime type safety

### Before Committing

```bash
npm run lint      # Check style
npm run format    # Auto-format code
npm run build     # Verify TypeScript compiles
npm run test      # Run tests
```

## 🔄 Development Workflow

### Adding a Feature

1. **Backend** — Define API contract in `src/types/index.ts`
2. **Backend** — Implement endpoint and business logic
3. **SDK** — Wrap the endpoint in `src/client.ts`
4. **Frontend** — Call SDK from component, no direct backend calls

### Code Review

- All changes go through pull requests
- Link related PRs across repos
- Verify contracts match across backend → SDK → frontend

## 🚢 Deployment

### Backend

Deploy to production server or Docker container:

```bash
npm run build
npm start
```

### SDK

Publish to npm (when ready):

```bash
npm run build
npm publish
```

### Frontend

Deploy to Vercel or Netlify:

```bash
npm run build
npm start
```

## 📞 Contributing

1. Fork the appropriate repo
2. Create a feature branch: `git checkout -b feature/my-feature`
3. Follow code standards (lint, format, test)
4. Open a pull request with clear description
5. Get review from team members

## 🤝 Support

- **Issues:** Report bugs in the relevant repo's Issues tab
- **Discussions:** Start conversations in GitHub Discussions
- **Documentation:** Check repo READMEs first

## 📄 License

TipForge is open source under the MIT License.

## 🌟 Key Features

- ✅ Instant USDC payments via Stellar
- ✅ Multi-platform creator profiles (X, Instagram, TikTok, YouTube, GitHub, Twitch)
- ✅ No geographic barriers or regional restrictions
- ✅ Low transaction fees powered by Stellar
- ✅ Simple onboarding for creators and fans
- ✅ Creator dashboard with earnings tracking
- ✅ Developer-friendly SDK for integrations
- ✅ Type-safe TypeScript throughout

## 🎯 Roadmap

**Phase 1 (Current)** — MVP

- Creator registration and verification
- Send tip functionality
- Basic dashboard

**Phase 2** — Scale

- Browser extension
- Mobile apps
- Payment links

**Phase 3** — Ecosystem

- Subscriptions
- Donations
- Merchant tools

---

**Built with ❤️ by the TipForge team**

Join us in making creator support frictionless, global, and accessible.
