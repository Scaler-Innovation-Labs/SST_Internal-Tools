

```markdown
# 🏫 SST Internal Tools – Unified Campus Platform

A monorepo project that consolidates key internal tools for Scaler School of Technology into a single platform, including:

- 🏠 **Hostel Management**
- 🍽️ **Mess Management**
- 💻 **E-Learning Hub**

This project uses a scalable **Monorepo structure with Turborepo**, a clean **MVC architecture for the backend**, and **React + Vite** for the frontend.

---

## 📁 Folder Structure

```
SST_Internal-Tools/
├── apps/
│   ├── web/              # React frontend (Vite)
│   └── backend/          # Node.js + Express backend (MVC)
├── packages/             # (optional) Shared libraries (auth, UI, config, utils)
├── .env.example          # Example environment file
├── .gitignore
├── package.json
├── turbo.json            # Turborepo configuration
└── README.md
```

---

## 🛠 Tech Stack

| Layer         | Technology                          |
|--------------|--------------------------------------|
| Frontend     | React, Vite, Tailwind CSS            |
| Backend      | Node.js, Express                     |
| Database     | PostgreSQL (via Prisma or raw SQL)   |
| Auth         | OAuth 2.0, JWT                       |
| Dev Tools    | Turborepo, Nodemon, ESLint           |
| Notifications| Firebase Cloud Messaging             |
| Payments     | Razorpay / UPI (for Mess Module)     |

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/Scaler-Innovation-Labs/SST_Internal-Tools.git
cd SST_Internal-Tools
```

---

### 2. Install Root Dependencies

```bash
npm install
```

> This installs dependencies across all apps using Turborepo workspaces.

---

### 3. Environment Setup

Create a `.env` file at the root or per app as needed. Start by copying from the example:

```bash
cp .env.example .env
```

Fill in your variables (e.g., DB connection, JWT secret, Firebase keys, etc.)

```env
PORT=8000
DATABASE_URL=postgres://...
JWT_SECRET=your_jwt
```

---

## 📦 Running the Apps

From the root of the repo:

```bash
npm run dev
```

> This will run **both the frontend and backend** in parallel using Turborepo.

---

## 🔧 Scripts

```bash
npm run dev       # Run all apps in dev mode
npm run build     # Build all apps
npm run lint      # Lint all apps
```

---

## 📂 Backend (MVC)

Located in `apps/backend/`

```
apps/backend/
├── controllers/        # Request logic (e.g., authController.js)
├── models/             # DB schema/models
├── routes/             # API endpoints (e.g., authRoutes.js)
├── services/           # Business logic
├── middlewares/        # Auth, error handling, etc.
├── utils/              # Utility functions
├── config/             # DB config and environment setup
└── app.js              # Entry point for Express server
```

Run it standalone:

```bash
cd apps/backend
npm install
npm run dev
```

---

## 🖥️ Frontend (React + Vite)

Located in `apps/web/`

Features basic routing setup with Tailwind CSS. Easily extendable for Hostel, Mess, and E-Learning flows.

Run it standalone:

```bash
cd apps/web
npm install
npm run dev
```

Open your browser at: `http://localhost:5173`

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

## Details - 
Feature Details in Depth will be Brainstormed between students in the Innovation Lab (Details for that will be shared soon)


```


