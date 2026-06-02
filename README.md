# 🎓 FACEPrep Interactive Java Slides

A modern, high-fidelity slide presentation platform built with **Slidev**, **Vue 3**, **Vite**, and **TailwindCSS**. The platform is secured by **Google OAuth 2.0** and features an administrative dashboard for email whitelist management, backed by **Firebase Firestore**.

---

## ✨ Features

- **📖 Interactive Decks**: Highly interactive slides built on Slidev, allowing components, custom CSS, animations, and live-code examples.
- **🔒 Google OAuth Authentication**: Fully secured slide viewing. Access is locked behind a glassmorphic login screen unless the user logs in with a whitelisted email.
- **🛠️ Admin Whitelist Dashboard**: A built-in administration modal for the primary administrator (`ponrajacc@gmail.com`) to add/remove whitelisted emails dynamically.
- **⚡ Serverless Backend API**: Vercel Serverless Functions (`/api/emails`) handle user whitelist authentication and verification using Google's secure `tokeninfo` endpoint.
- **🔥 Firebase Firestore Database Integration**: Real-time cloud database syncing for the whitelist, with a local file fallback (`allowed-emails.json`) for local development.
- **📦 Session Script Automation**: Automatic script generators to easily create, validate, and manage individual session decks (e.g., `dev:01`, `build:01`, `dev:02`).

---

## 🛠️ Technology Stack

- **Frontend**: [Slidev](https://sli.dev/) (Vite, Vue 3, TypeScript, Monaco Editor, Lucide Icons)
- **Styling**: Vanilla CSS with custom theme variables, responsive design, and glassmorphic micro-animations.
- **Authentication**: Google Identity Services SDK (Google OAuth 2.0)
- **Backend & Database**: Vercel Serverless Functions (Node.js), Firebase SDK & Firestore
- **Deployment**: Vercel

---

## 🚀 Getting Started

### 📋 Prerequisites

- **Node.js**: `v22.0` or higher
- **Google Cloud Console Project**: Set up a project with Google Sign-in enabled, and obtain your Client ID.
- **Firebase Project**: A Firestore database to persist the email whitelist.

### ⚙️ Setup & Configuration

1. **Clone the Repository** and navigate to the project directory.

2. **Install Dependencies**:
   ```bash
   npm install
   ```

3. **Configure Environment Variables**:
   Create a `.env` file in the root directory (already added to `.gitignore`):
   ```env
   # Add any environment variables here
   ```

4. **Verify Google OAuth Client ID**:
   The frontend Google OAuth client ID is configured in `api/emails.js` and `src/components/LoginOverlay.vue`. Ensure it matches your Authorized JavaScript Origins.

5. **Initialize Firebase Config**:
   In `api/emails.js`, verify the `firebaseConfig` credentials map to your Firestore database.

---

## 💻 Script Commands

Run and build specific session decks using standard `npm run` commands:

| Action | Command | Description |
|---|---|---|
| **Start Dev Server (Session 1)** | `npm run dev:01` | Runs the Introduction to Java slides (`src/01-introduction-to-java.md`) |
| **Start Dev Server (Session 2)** | `npm run dev:02` | Runs the Java Fundamentals slides (`src/02-java-fundamentals.md`) |
| **Start Dev Server (Session 3)** | `npm run dev:03` | Runs the Operators slides (`src/03-operators.md`) |
| **Build Session 1** | `npm run build:01` | Compiles Session 1 for production deployment |
| **Build Session 2** | `npm run build:02` | Compiles Session 2 for production deployment |
| **Build Session 3** | `npm run build:03` | Compiles Session 3 for production deployment |
| **Create New Deck** | `npm run new:deck` | Custom script to generate a new Slidev deck |
| **Generate Session** | `npm run workflow:new` | Interactive script to generate a new slide session and auto-update npm scripts |
| **List Sessions** | `npm run template:list` | Lists all slide sessions available in `src` |
| **Local Preview** | `npm run preview` | Serves the built static site from `dist` locally |

---

## 📁 Project Structure

```
slidev-pro/
├── api/                   # Vercel Serverless Function Endpoints
│   ├── emails.js          # Whitelist CRUD operations & Google token verification
│   └── run.js             # Dev runner / mock server utilities
├── scripts/               # Automation scripts for Slidev builds & template workflows
├── src/                   # Slides source code
│   ├── 01-introduction-to-java.md  # Session 1 content
│   ├── 02-java-fundamentals.md     # Session 2 content
│   ├── 03-operators.md             # Session 3 content
│   ├── Slide/             # Custom slide components & layouts
│   ├── components/        # Vue reusable components (e.g. LoginOverlay.vue)
│   ├── auth.ts            # Reactive authentication store
│   ├── global-bottom.vue  # App layout wrapper (Auth & Admin Dashboard insertion)
│   └── style.css          # Core design system stylesheet
├── vercel.json            # Vercel Serverless Functions deployment configuration
├── allowed-emails.json    # Local fallback whitelisted emails (Git ignored)
└── package.json           # Scripts and dependencies definition
```

---

## 🔒 Security & Whitelist Verification Flow

1. **Authentication request**: A user attempts to access the slide deck.
2. **Access Control**: The `LoginOverlay` component intercepts requests, locking all content under a full-page blur.
3. **Google Sign-In**: The user signs in with their Google Account.
4. **Token Verification**:
   - The user's ID token is sent to the Vercel Serverless API (`/api/emails`).
   - The API verifies the token with Google’s OAuth tokeninfo endpoint.
   - The verified email is checked against the whitelist in **Firebase Firestore** (or the local fallback list).
5. **Session Resolution**: If whitelisted, access is granted. If the user is the main administrator (`ponrajacc@gmail.com`), the Admin Panel gear is rendered in the footer, permitting email adds/deletions.
