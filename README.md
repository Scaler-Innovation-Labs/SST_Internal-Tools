# 🏫 SST Internal Tools – Unified Campus Platform

A monorepo project that consolidates key internal tools for Scaler School of Technology into a single platform, including:

- 🏠 **Hostel Management**
- 🍽️ **Mess Management**
- 💻 **E-Learning Hub**

This project uses a scalable **Monorepo structure with Turborepo**, a clean **MVC architecture for the backend**, and **React + Vite** for the frontend.

---

## 📁 Folder Structure

- **Turborepo structure**
- **MVC backend (Node.js + Express)**
- **Frontend using React + Vite**
- **Future packages (shared UI, auth, utils)**

---

## ✅ Monorepo Folder Architecture for SST_Internal-Tools

SST_Internal-Tools/
├── apps/               # All runnable applications
│   ├── backend/        # Node.js + Express backend (MVC)
│   │   ├── controllers/   # Handles request logic (e.g., userController.js)
│   │   ├── models/        # Database models/schema definitions
│   │   ├── routes/        # Express routes (e.g., userRoutes.js)
│   │   ├── services/      # Business logic (used by controllers)
│   │   ├── middlewares/   # Reusable middleware (e.g., authMiddleware.js)
│   │   ├── config/        # DB connection, environment setup
│   │   ├── utils/         # Helper utilities (e.g., token, logger)
│   │   ├── app.js         # Express app setup
│   │   └── server.js      # Entry point to start the server
│   │
│   └── web/            # React frontend (Vite)
│       ├── public/        # Static files (favicon, etc.)
│       ├── src/
│       │   ├── components/  # Reusable UI components (Button, Card)
│       │   ├── pages/       # Page-level views (Home.jsx, Dashboard.jsx)
│       │   ├── routes/      # React Router configuration
│       │   ├── services/    # API services (axios instances)
│       │   ├── utils/       # Frontend utilities (formatters, validators)
│       │   ├── App.jsx      # Main App entry
│       │   └── main.jsx     # React DOM renderer
│       ├── index.html
│       └── vite.config.js
│
├── packages/           # Shared code across apps
│   ├── ui/             # (Optional) Shared design system (Button, Modal, etc.)
│   ├── auth/           # (Optional) Authentication logic (JWT handling, roles)
│   ├── config/         # (Optional) Shared configurations (Tailwind, ESLint, etc.)
│   └── utils/          # (Optional) Shared utilities (validators, date utils)
│
├── .env.example        # Example environment file
├── .gitignore          # Ignore node_modules, .env, etc.
├── package.json        # Root-level scripts and workspace definition
├── turbo.json          # Turborepo pipeline configuration
└── README.md           # Project overview and usage

---

## 💡 Folder Breakdown

### 🧠 apps/backend (MVC)

- **controllers/** → Handle HTTP requests and call services
- **models/** → Define your data structure (with Mongoose, Sequelize, Prisma, etc.)
- **routes/** → API endpoints (e.g., `/auth`, `/students`, `/hostel`)
- **services/** → Business logic, often reusable by multiple controllers
- **middlewares/** → e.g., authentication, error handling, validation
- **config/** → Database setup, third-party configs
- **utils/** → Custom logger, token handler, etc.
- **app.js** → Sets up Express app and middleware
- **server.js** → Boots up the server

---

### 💻 apps/web (React + Vite)

- **components/** → Reusable UI blocks like `<Button />`, `<Navbar />`
- **pages/** → Route-linked views like `Dashboard`, `LeaveForm`
- **routes/** → React Router setup with layout wrappers
- **services/** → Axios instance, API call logic
- **utils/** → Any helper functions
- **main.jsx / App.jsx** → App setup with router and layout

---

### 📦 packages/ (Optional but scalable)

Start empty or create:

- **ui/** → Shared design components (used in web + admin panels)
- **auth/** → Shared auth utilities (JWT decode, protected routes, role guards)
- **config/** → Tailwind config, tsconfig, eslint settings

---

## ✅ Turborepo-Specific Notes

### package.json (root)

```json
{
  "private": true,
  "workspaces": ["apps/*", "packages/*"],
  "scripts": {
    "dev": "turbo run dev --parallel",
    "build": "turbo run build",
    "lint": "turbo run lint"
  },
  "devDependencies": {
    "turbo": "^1.12.0"
  }
}
```
