# E-Voting System

Full-stack MERN e-voting app with role-based access for admins and voters. The backend provides REST APIs for auth, elections, and voting, while the frontend offers dashboards and protected routes.

## Features
- JWT auth with role-based routes (admin, voter)
- Election CRUD (admin)
- Vote casting and results access
- Protected React routes and persisted auth state

## Tech Stack
- Backend: Node.js, Express, MongoDB, Mongoose, JWT
- Frontend: React, Vite, Tailwind CSS, Axios, React Router

## Project Structure
```
backend/   # Express API and MongoDB models
frontend/  # React + Vite client
```

## Prerequisites
- Node.js 14+ and npm
- MongoDB (local or Atlas)

## Backend Setup
1) Install dependencies
```bash
cd backend
npm install
```

2) Create a .env file in backend/
```bash
NODE_ENV=development
PORT=5000
MONGO_URI=mongodb://127.0.0.1:27017/eVotingDB
JWT_SECRET=your_jwt_secret
```

3) Start the API server
```bash
npm run dev
```

The API runs on http://localhost:5000.

## Frontend Setup
1) Install dependencies
```bash
cd frontend
npm install
```

2) Configure the API base URL
The frontend Axios instance currently uses a hardcoded base URL in [frontend/src/api/axios.js](frontend/src/api/axios.js). Update it if your backend runs elsewhere.

3) Start the client
```bash
npm run dev
```

The app runs on http://localhost:5173.

## API Overview
Common endpoints (see [backend/README.md](backend/README.md) for details):
- POST /api/auth/register
- POST /api/auth/login
- GET /api/elections
- GET /api/elections/:id
- POST /api/elections
- PUT /api/elections/:id
- DELETE /api/elections/:id
- POST /api/votes
- GET /api/votes

## Notes
- Auth state is stored in localStorage in the frontend context provider.
- CORS is configured for http://localhost:5173 in the backend server.

## Scripts
Backend (from [backend/package.json](backend/package.json)):
- npm run dev
- npm start

Frontend (from [frontend/package.json](frontend/package.json)):
- npm run dev
- npm run build
- npm run preview

## Next Steps
- Add a .env.example for backend and frontend
- Document admin seeding and test users
- Add API docs or OpenAPI spec
