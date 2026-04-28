# Frontend — e-voting-system

React + Vite frontend for the e-voting system. Implements UI for admins and voters, communicates with the backend API.

## ✅ Quick start

Prerequisites:
- Node.js (14+)
- npm or yarn

Install and run:

```bash
cd frontend
npm install
npm run dev
```

Build and preview:

```bash
npm run build
npm run preview
```

## ⚙️ Environment variables
Create a `.env` or `.env.local` in `frontend/` (Vite requires variables to start with `VITE_`):

```
VITE_API_URL=http://localhost:5000/api
```

The `api/axios.js` file reads the API base URL from `VITE_API_URL`.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend using TypeScript with type-aware lint rules enabled. Check out the [TS template](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-react-ts) for information on how to integrate TypeScript and [`typescript-eslint`](https://typescript-eslint.io) in your project.

## 📁 Directory structure

```
frontend/
├─ package.json
├─ index.html
├─ vite.config.js
├─ public/
├─ src/
│  ├─ main.jsx               # app entry
│  ├─ index.css              # global styles
│  ├─ App.jsx                # main app shell
│  ├─ api/
│  │  └─ axios.js            # axios instance (baseURL from VITE_API_URL)
│  ├─ assets/
│  ├─ components/
│  │  ├─ Navbar.jsx
│  │  └─ ProtectedRoute.jsx
│  ├─ context/
│  │  └─ AuthContext.jsx    # auth state / token handling
│  ├─ pages/
│  │  ├─ AdminDashboard.jsx
│  │  ├─ CreateElectionPage.jsx
│  │  ├─ ElectionDetailsPage.jsx
│  │  ├─ ElectionsPage.jsx
│  │  ├─ HomePage.jsx
│  │  ├─ LoginPage.jsx
│  │  ├─ NotFoundPage.jsx
│  │  ├─ RegisterPage.jsx
│  │  ├─ UpdateStatusPage.jsx
│  │  ├─ VoterDashboard.jsx
│  │  └─ welcome.jsx
│  └─ router/
│     └─ AppRouter.jsx       # app routing
└─ eslint.config.js
```

## 🔧 Notes
- Authentication state is managed in `AuthContext` and likely persisted to `localStorage` (check the file for exact behavior).
- `ProtectedRoute.jsx` is used to guard private routes (admin / voter dashboards).
- Make sure `VITE_API_URL` points to your running backend (e.g., `http://localhost:5000/api`).

## 📌 Tips
- Use `npm run dev` for local development (Vite hot reload is enabled).
- When reporting bugs, include console logs and API request/response details from the browser network tab.

---

If you'd like, I can add a `.env.example` and a short developer-contribution section.
