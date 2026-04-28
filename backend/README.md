# Backend — e-voting-system

A minimal Express.js backend for the e-voting system. Provides authentication, election management, and voting APIs connected to MongoDB.

## ✅ Quick start

Prerequisites:
- Node.js (14+)
- npm or yarn
- MongoDB instance (local or Atlas)

Install and run:

```bash
cd backend
npm install
# start in development (if nodemon is configured)
npm run dev
# or start production
npm start
```

> Tip: Check the `scripts` section in `package.json` for the exact commands used in this project.

## ⚙️ Environment variables (.env)
Create a `.env` file in `backend/` with values similar to:

```
MONGO_URI=your_mongo_connection_string
JWT_SECRET=your_jwt_secret
PORT=5000
```

## 📁 Directory structure

```
backend/
├─ package.json
├─ server.js                # App entry point
├─ config/
│  └─ db.js                 # MongoDB connection helper
├─ controllers/
│  ├─ authController.js     # register / login
│  ├─ electionController.js # election CRUD
│  └─ voteController.js     # vote creation and reporting
├─ middleware/
│  ├─ authMiddleware.js     # protects routes / checks JWT
│  └─ errorMiddleware.js    # central error handler
├─ models/
│  ├─ Election.js
│  ├─ User.js
│  └─ Vote.js
├─ routes/
│  ├─ authRoutes.js
│  ├─ electionRoutes.js
│  └─ voteRoutes.js
└─ utils/
   └─ generateToken.js      # JWT helper
```

## 🔌 API (common endpoints)

- POST `/api/auth/register` — create a new user
- POST `/api/auth/login` — login and receive JWT
- GET `/api/elections` — list elections
- GET `/api/elections/:id` — election details
- POST `/api/elections` — create election (admin)
- PUT `/api/elections/:id` — update election (admin)
- DELETE `/api/elections/:id` — delete election (admin)
- POST `/api/votes` — cast a vote
- GET `/api/votes` — list votes / results (admin)

(Exact routes and behaviors are implemented in `routes/` and `controllers/`—refer to the files for details.)

## 🛠️ Development notes
- The DB connection is handled in `config/db.js` — ensure `MONGO_URI` is correct.
- Authentication uses JWTs (see `utils/generateToken.js` and `middleware/authMiddleware.js`).
- Use Postman / Insomnia or the front-end to test the APIs.

## 📌 Troubleshooting
- If the server fails to connect to MongoDB, verify `MONGO_URI` and network access (Atlas whitelist / local Mongo running).
- Check `server.js` logs for start-up and connection errors.

---