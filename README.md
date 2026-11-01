# ✈️ TravelMate — AI-Powered Travel Booking App

> A full-stack travel booking web application with AI chatbot assistance, built with React, TypeScript, Vite, Tailwind CSS, and Supabase.

---

## 📸 Project Overview

TravelMate is a modern travel companion app that lets users:
- 🔍 **Search & book flights, hotels, and cabs**
- 🤖 **Chat with an AI travel assistant** (powered by Supabase Edge Functions)
- 🌙 **Toggle dark/light theme**
- 💾 **Save and manage trips**
- 👤 **Manage user profile and settings**
- 🛒 **Cart system** for booking management

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| **React 18** | Frontend UI library |
| **TypeScript** | Type-safe JavaScript |
| **Vite** | Fast build tool & dev server |
| **Tailwind CSS** | Utility-first styling |
| **shadcn/ui** | Pre-built accessible components |
| **Supabase** | Backend (Auth + Database + Edge Functions) |
| **React Router v6** | Client-side routing |
| **TanStack Query** | Server state management |
| **Framer Motion** | Animations |
| **Recharts** | Data visualization |
| **Zod + React Hook Form** | Form validation |

---

## ✅ Prerequisites

Make sure the following are installed on your system before running the project:

| Tool | Version | Download |
|---|---|---|
| **Node.js** | v18 or higher | https://nodejs.org |
| **npm** | v9 or higher (comes with Node) | — |
| **Git** | Any recent version | https://git-scm.com |

To check if already installed:
```bash
node --version
npm --version
git --version
```

---

## 🚀 Getting Started (Run Locally)

### Step 1 — Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
cd YOUR_REPO_NAME
```

### Step 2 — Install Dependencies

```bash
npm install
```

> ⏳ This may take a minute. It installs all required packages from `package.json`.

### Step 3 — Set Up Environment Variables

Create a `.env` file in the **root of the project** (same folder as `package.json`):

```bash
# On Windows (Command Prompt):
copy .env.example .env

# On Mac/Linux:
cp .env.example .env
```

Then open `.env` and fill in your Supabase credentials:

```env
VITE_SUPABASE_URL=your_supabase_project_url
VITE_SUPABASE_PUBLISHABLE_KEY=your_supabase_anon_key
VITE_SUPABASE_PROJECT_ID=your_supabase_project_id
```

> 📌 **Where to get these?** See the [Supabase Setup](#-supabase-setup-for-backend) section below.

### Step 4 — Start the Development Server

```bash
npm run dev
```

Open your browser and go to: **http://localhost:8080**

🎉 The app should now be running!

---

## 🔑 Supabase Setup (For Backend)

This app uses **Supabase** as its backend (database + authentication + AI chat functions).

### Option A — Use the Existing Supabase Project (Recommended for Quick Testing)

The `.env.example` file already contains working credentials for the demo Supabase project. Just copy it to `.env` and you're ready to go — no extra setup needed.

### Option B — Create Your Own Supabase Project

1. Go to https://supabase.com and create a free account
2. Click **"New Project"** and fill in the details
3. Once created, go to **Settings → API**
4. Copy:
   - `Project URL` → paste as `VITE_SUPABASE_URL`
   - `anon / public` key → paste as `VITE_SUPABASE_PUBLISHABLE_KEY`
   - Project Reference ID (from URL) → paste as `VITE_SUPABASE_PROJECT_ID`
5. Run the database migrations by going to **SQL Editor** in your Supabase dashboard and running each file inside `/supabase/migrations/` in order

---

## 📁 Project Structure

```
travelmate/
├── public/                  # Static assets (favicon, robots.txt)
├── src/
│   ├── assets/              # Images (hero background, logo)
│   ├── components/          # Reusable UI components
│   │   ├── ui/              # shadcn/ui base components
│   │   ├── Navbar.tsx
│   │   ├── ChatSidebar.tsx  # AI Chat assistant
│   │   ├── CartDrawer.tsx
│   │   └── ...
│   ├── contexts/            # Global state (Cart, Theme)
│   ├── data/                # Static data (Indian cities, mock data)
│   ├── hooks/               # Custom React hooks
│   ├── integrations/
│   │   └── supabase/        # Supabase client & TypeScript types
│   ├── lib/                 # Utility functions
│   ├── pages/               # Route-level page components
│   │   ├── Auth.tsx         # Login / Sign Up
│   │   ├── Dashboard.tsx    # Home page
│   │   ├── FlightBooking.tsx
│   │   ├── HotelBooking.tsx
│   │   ├── CabBooking.tsx
│   │   ├── Profile.tsx
│   │   ├── SavedTrips.tsx
│   │   ├── Settings.tsx
│   │   └── ...
│   ├── App.tsx              # Root component with routing
│   ├── main.tsx             # App entry point
│   └── index.css            # Global styles
├── supabase/
│   ├── functions/
│   │   └── chat/            # AI chatbot Edge Function
│   └── migrations/          # Database schema SQL files
├── .env.example             # Template for environment variables
├── .gitignore
├── package.json
├── tailwind.config.ts
├── tsconfig.json
└── vite.config.ts
```

---

## 📜 Available Scripts

Run these from the project root folder:

| Command | Description |
|---|---|
| `npm run dev` | Start development server at http://localhost:8080 |
| `npm run build` | Build the app for production |
| `npm run preview` | Preview the production build locally |
| `npm run lint` | Run ESLint to check for code issues |

---

## 🌐 Pages & Routes

| Route | Page | Description |
|---|---|---|
| `/` | Dashboard | Home page with destination cards |
| `/auth` | Auth | Login and Sign Up |
| `/flights` | FlightBooking | Search and book flights |
| `/hotels` | HotelBooking | Search and book hotels |
| `/cabs` | CabBooking | Book cab rides |
| `/profile` | Profile | User profile management |
| `/saved-trips` | SavedTrips | View saved/booked trips |
| `/settings` | Settings | App preferences |
| `/faq` | FAQ | Frequently Asked Questions |
| `/contact` | Contact | Contact form |
| `/privacy` | Privacy | Privacy Policy |
| `/terms` | Terms | Terms & Conditions |

---

## ⚙️ Environment Variables Reference

Create a `.env` file at the project root with these variables:

```env
# Required — Supabase backend configuration
VITE_SUPABASE_URL=https://your-project-id.supabase.co
VITE_SUPABASE_PUBLISHABLE_KEY=your-anon-public-key
VITE_SUPABASE_PROJECT_ID=your-project-id
```

> ⚠️ **Never commit your `.env` file to GitHub.** It is already listed in `.gitignore` for safety.

---

## 🔒 Security Notes

- The `VITE_SUPABASE_PUBLISHABLE_KEY` is an **anon/public key** — it is safe to use in frontend code
- Never expose service role keys or private keys in environment variables prefixed with `VITE_`
- Authentication is handled securely by Supabase Auth

---

## 🐞 Troubleshooting

**`npm install` fails:**
- Make sure Node.js version is 18 or above: `node --version`
- Try deleting `node_modules/` folder and running `npm install` again

**App loads but shows a blank page:**
- Check that your `.env` file exists with the correct Supabase credentials
- Open browser DevTools (`F12`) → Console tab to see error messages

**Port already in use error:**
- Another application may be running on port 8080
- Stop it, or change the port in `vite.config.ts`

**Supabase connection error:**
- Double-check the values in your `.env` file
- Make sure there are no extra spaces or quotes around the values

---

## 👨‍💻 Author

Developed as part of a college project.  
Built with ❤️ using React, TypeScript, and Supabase.


---

## 🛡️ Additional project: Sentinel-X

This repository also contains **Sentinel-X**, a separate defensive cybersecurity and applied-ML portfolio demo.

- [Open Sentinel-X project](./SentinelX_Project/)
- [Sentinel-X setup and documentation](./SentinelX_Project/README.md)
- [Sentinel-X source code](./SentinelX_Project/src/)
- [Sentinel-X automated tests](./SentinelX_Project/tests/)

Sentinel-X is a local honeypot simulation. It detects suspicious input in its own demo portal, records incidents locally, and applies a temporary lockout to that portal. It does not access or retaliate against other systems. See its README for setup, privacy notes, limitations, and authorized-use guidance.
