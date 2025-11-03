
---

# 🩸 Blood Bank 

A modern frontend for a blood bank management system built with **Vite + React + TypeScript**, integrated with **Supabase** for authentication and database, and styled using **Tailwind CSS**.

This repository includes both the UI and a Supabase SQL migration (`supabase/migrations`) to set up the database schema.

---

## 🚀 Tech Stack Overview

| Feature        | Stack / Tool                          |
|----------------|----------------------------------------|
| Framework      | Vite + React + TypeScript              |
| Styling        | Tailwind CSS + PostCSS                 |
| Auth & DB      | Supabase (`@supabase/supabase-js`)     |
| Purpose        | Manage donors, hospitals, inventory, requests, and admin dashboards |

---

## ⚙️ Requirements

- **Node.js** 18+ (recommended)
- **npm** or **pnpm**
- *(Optional)* Supabase account or local Supabase setup for DB migrations

---

## 📁 Project Structure

```
├── src/
│   ├── main.tsx               # App entry point
│   ├── App.tsx                # Routes & app shell
│   ├── index.css              # Global Tailwind styles
│   ├── components/            # Role-based components (Admin, Donor, Hospital, Auth)
│   ├── contexts/AuthContext.tsx  # Auth state via React Context
│   └── lib/supabase.ts        # Supabase client setup
│
├── supabase/migrations/
│   └── 20251015130704_create_blood_bank_schema.sql
│
├── package.json               # Scripts & dependencies
```

---

## 🔐 Environment Setup

Create a `.env.local` file in the root with:

```env
VITE_SUPABASE_URL=https://your-project.supabase.co
VITE_SUPABASE_ANON_KEY=your-anon-public-key

# Optional (server-side only)
# SUPABASE_SERVICE_ROLE_KEY=your-service-role-key
```

> ⚠️ Vite requires public-facing env variables to start with `VITE_`. Keep service role keys private and server-only.

---

## 📦 Installation

Open PowerShell in the project root and run:

```powershell
npm install
```

---

## 🧪 Development Scripts

| Script              | Description                          |
|---------------------|--------------------------------------|
| `npm run dev`       | Start Vite dev server (hot reload)   |
| `npm run build`     | Build production assets              |
| `npm run preview`   | Preview production build locally     |
| `npm run lint`      | Run ESLint                          |
| `npm run typecheck` | Run TypeScript type checking         |

Example:

```powershell
npm run dev
```

Open [http://localhost:5173](http://localhost:5173) in your browser.

---

## 🗃️ Database Migrations

Migration file:  
`supabase/migrations/20251015130704_create_blood_bank_schema.sql`

Apply using:

### Supabase CLI (recommended)

```powershell
supabase login
supabase link --project-ref <project-ref>
supabase db push
```

### PostgreSQL (psql)

```powershell
psql "postgresql://user:pass@host:5432/dbname" -f supabase/migrations/20251015130704_create_blood_bank_schema.sql
```

> Adjust credentials and paths as needed.

---

## 🔌 Supabase Client

Located in `src/lib/supabase.ts`.  
Reads `VITE_SUPABASE_URL` and `VITE_SUPABASE_ANON_KEY` from `.env`.

> For server-only operations, use service keys in backend/serverless functions — never expose them in client code.

---

## 🛠️ Dev Notes

- **Add a route/component**: Create under `src/components/<Role>/` and register in `App.tsx`.
- **Auth**: Use `AuthContext.tsx` for centralized auth state and hooks.
- **Styling**: Tailwind is ready to go — use utility classes freely.

---

## 🧪 Testing (Future Work)

Consider adding:

- Unit tests with **Vitest** or **Jest**
- Integration tests with **React Testing Library**

---

## ✅ Linting & Type Checking

```powershell
npm run lint       # Check lint errors
npm run typecheck  # Run TypeScript checks
```

---

## 🚀 Deployment

Build and deploy the `dist/` folder to:

- Netlify
- Vercel
- AWS S3 + CloudFront
- GitHub Pages

```powershell
npm run build
```

> Ensure `VITE_SUPABASE_URL` and `VITE_SUPABASE_ANON_KEY` are set in your host’s environment settings.

---

## 🤝 Contribution Guide

1. Fork the repo  
2. Create a feature branch  
3. Make changes and add tests  
4. Open a PR with a clear description

Before submitting:

```powershell
npm run lint
npm run typecheck
```

---

## 🔒 Security Notes

- Never commit secrets or service role keys.
- Keep service keys strictly server-side.

---

## 📜 License

This project currently has no license.  
To open-source it, add a `LICENSE` file (e.g., MIT).

---

## 💡 Optional Enhancements

Let me know if you'd like me to add:

- ✅ `CONTRIBUTING.md` with PR checklist  
- ✅ `.env.local.example` file  
- ✅ CI workflow for lint/typecheck and preview builds

Just say the word and I’ll generate them for you!

---

Would you like me to turn this into a shareable page or help you publish it to GitHub with formatting?
