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
├── apps/ # All runnable applications go here
│ ├── E-Learning_Hub/ # E-Learning Hub Application
│ │ ├── backend/ # Backend for E-Learning Hub (Node.js + Express API)
│ │ │ ├── controllers/ # Handles request logic (e.g., courseController.js)
│ │ │ ├── models/ # Database models/schema definitions (e.g., Course.js)
│ │ │ ├── routes/ # Express routes (e.g., courseRoutes.js)
│ │ │ ├── services/ # Business logic used by controllers
│ │ │ ├── middlewares/ # Middleware functions (e.g., authMiddleware.js)
│ │ │ ├── config/ # Database connections & environment setup
│ │ │ ├── utils/ # Helper utilities (e.g., token generation, logging)
│ │ │ ├── app.js # Express application setup
│ │ │ └── server.js # Main entry point to start the Express server
│ │ ├── web/ # Frontend for E-Learning Hub (React + Vite)
│ │ │ ├── public/ # Static files (favicon, etc.)
│ │ │ ├── src/
│ │ │ │ ├── components/ # Reusable UI components (e.g., Button, Modal)
│ │ │ │ ├── pages/ # Page-level views (Dashboard.jsx, CoursePage.jsx)
│ │ │ │ ├── routes/ # React Router configuration
│ │ │ │ ├── services/ # API services (Axios instances)
│ │ │ │ ├── utils/ # Frontend utilities (formatters, validators)
│ │ │ │ ├── App.jsx # Main application entry
│ │ │ │ └── main.jsx # React DOM renderer
│ │ │ ├── index.html # Main HTML file
│ │ │ └── vite.config.js # Vite configuration file
│ │
│ ├── Hostel_Management/ # Hostel Management Application
│ │ ├── backend/ # Same backend structure as E-Learning Hub
│ | |  
│ │ ├── web/ # Same frontend structure as E-Learning Hub
│ │  
│
│ ├── Mess_Management/ # Mess Management Application
│ │ ├── backend/ # Same backend structure as above
│ │ ├── web/ # Same frontend structure as above
│
├── .env.example # Example environment variables for setup
├── .gitignore # Ignore node_modules, .env, etc.
├── package.json # Root-level scripts and workspace definition
├── turbo.json # Turborepo pipeline configuration
└── README.md # Documentation

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
