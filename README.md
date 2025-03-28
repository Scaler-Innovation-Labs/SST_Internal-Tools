# 🏫 SST Internal Tools – Unified Campus Platform

A monorepo project that consolidates key internal tools for Scaler School of Technology into a single platform, including:

- 🏠 **Hostel Management**
- 🍽️ **Mess Management**
- 💻 **E-Learning Hub**

This project uses a scalable **Monorepo structure with Turborepo**, a clean **MVC architecture for the backend**, and **React + Vite** for the frontend.

---

## 📁 Folder Structure

### ✅ Monorepo Folder Architecture for SST_Internal-Tools

```
SST_Internal-Tools/
├── apps/                             # All runnable apps go here
│   ├── backend/                      # Node.js + Express backend (MVC)
│   │   ├── controllers/              # Handle request logic (e.g., userController.js)
│   │   ├── models/                   # DB models/schema definitions
│   │   ├── routes/                   # Express routes (e.g., userRoutes.js)
│   │   ├── services/                 # Business logic (used by controllers)
│   │   ├── middlewares/              # Reusable middleware (e.g., authMiddleware.js)
│   │   ├── config/                   # DB connection, environment setup
│   │   ├── utils/                    # Helper utilities (e.g., token, logger)
│   │   ├── app.js                    # Express app setup
│   │   └── server.js                 # Entry point to start the server
│   │
│   └── web/                          # React frontend (Vite)
│       ├── public/                   # Static files (favicon, etc.)
│       ├── src/
│       │   ├── components/           # Reusable UI components (e.g., Button, Card)
│       │   ├── pages/                # Page-level views (Home.jsx, Dashboard.jsx)
│       │   ├── routes/               # React Router config
│       │   ├── services/             # API services (e.g., axios instances)
│       │   ├── utils/                # Frontend utilities (formatters, validators)
│       │   ├── App.jsx               # Main App entry
│       │   └── main.jsx              # React DOM renderer
│       ├── index.html
│       └── vite.config.js
│
├── packages/                         # Shared code across apps
│   ├── ui/                           # (Optional) Shared design system (Button, Modal, etc.)
│   ├── auth/                         # (Optional) Auth-related logic (JWT handling, roles)
│   ├── config/                       # (Optional) Shared config like tailwind, eslint, etc.
│   └── utils/                        # (Optional) Shared utilities (validators, date utils, etc.)
│
├── .env.example                      # Example environment file for setup
├── .gitignore                        # Ignore node_modules, .env, etc.
├── package.json                      # Root-level scripts and workspace definition
├── turbo.json                        # Turborepo pipeline config
└── README.md                         # Project overview and usage
```

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

### 💻 apps/web (React + Vite)
- **components/** → Reusable UI blocks like `<Button />`, `<Navbar />`
- **pages/** → Route-linked views like `Dashboard`, `LeaveForm`
- **routes/** → React Router setup with layout wrappers
- **services/** → Axios instance, API call logic
- **utils/** → Any helper functions
- **main.jsx / App.jsx** → App setup with router and layout

### 📦 packages/ (Optional but scalable)
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

### turbo.json
```json
{
  "$schema": "https://turborepo.org/schema.json",
  "pipeline": {
    "dev": {
      "cache": false,
      "persistent": true
    },
    "build": {
      "outputs": ["dist/**"]
    },
    "lint": {}
  }
}
```

---

## 🚀 Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/Scaler-Innovation-Labs/SST_Internal-Tools.git
cd SST_Internal-Tools
```

### 2. Install Root Dependencies
```bash
npm install
```
> This installs dependencies across all apps using Turborepo workspaces.

### 3. Environment Setup
Create a `.env` file at the root or per app as needed.
```bash
cp .env.example .env
```
Fill in your variables (e.g., DB connection, JWT secret, Firebase keys, etc.)
```env
PORT=8000
DATABASE_URL=postgres://...
JWT_SECRET=your_jwt
```

### 📦 Running the Apps
```bash
npm run dev
```
> This will run **both the frontend and backend** in parallel using Turborepo.

### 🔧 Scripts
```bash
npm run dev       # Run all apps in dev mode
npm run build     # Build all apps
npm run lint      # Lint all apps
```

---

## 🧪 Future Add-ons
- [ ] Auth system (OAuth + JWT + RBAC)
- [ ] Shared UI package (`packages/ui`)
- [ ] Central notification service
- [ ] Database ORM setup (Prisma or Mongoose)
- [ ] CI/CD with GitHub Actions

---

## 🤝 Contributing
1. Fork the repo
2. Create your feature branch: `git checkout -b feature/my-feature`
3. Commit your changes: `git commit -m "Add some feature"`
4. Push to the branch: `git push origin feature/my-feature`
5. Open a pull request

---

## 📄 License
MIT © Scaler Innovation Labs

## 🧠 Innovation Lab Collaboration
Feature details will be brainstormed collaboratively by students in the Innovation Lab. More details to follow soon!

