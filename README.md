# Acme Dashboard

A full-stack invoice management dashboard built with Next.js App Router. Tracks customers, invoices, and revenue for a fictional company called Acme.

## Features

- **Authentication** — credential-based login via NextAuth v5
- **Dashboard overview** — revenue chart, latest invoices, and summary cards
- **Invoices** — create, edit, and delete invoices with server-side validation
- **Customers** — view customers with aggregated invoice totals
- **Search & pagination** — URL-based, works with server components
- **Responsive layout** — side nav collapses to a mobile bottom nav
- **Loading states** — skeleton UI via React Suspense streaming

## Tech Stack

- [Next.js](https://nextjs.org) (App Router, Turbopack)
- [TypeScript](https://www.typescriptlang.org)
- [Tailwind CSS](https://tailwindcss.com)
- [PostgreSQL](https://www.postgresql.org) via the `postgres` package
- [NextAuth v5](https://authjs.dev) — credentials provider
- [Zod](https://zod.dev) — form and server action validation
- [bcrypt](https://github.com/kelektiv/node.bcrypt.js) — password hashing

## Getting Started

**Prerequisites:** Node.js 18+, pnpm, a PostgreSQL database

1. Install dependencies:
   ```bash
   pnpm install
   ```

2. Set up environment variables — copy `.env.example` to `.env` and fill in:
   ```
   POSTGRES_URL=
   AUTH_SECRET=
   ```

3. Seed the database:
   ```
   GET /seed
   ```

4. Start the dev server:
   ```bash
   pnpm dev
   ```

Open [http://localhost:3000](http://localhost:3000) and log in with your seeded credentials.

## Project Structure

```
app/
├── dashboard/
│   ├── (overview)/     # Dashboard home with revenue & invoice summaries
│   ├── invoices/       # Invoice list, create, and edit pages
│   └── customers/      # Customer list page
├── login/              # Login page
├── lib/
│   ├── actions.tsx     # Server actions (create/update/delete invoices, auth)
│   ├── data.ts         # Database query functions
│   └── definitions.ts  # Shared TypeScript types
└── ui/                 # Shared components (nav, cards, forms, skeletons)
```
