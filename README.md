# Electronic-Voting System

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&height=190&text=E-Voting%20System&fontAlignY=38&fontSize=34&color=0:1e3a8a,100:0ea5e9&desc=Secure%20Digital%20Voting%20Platform%20%7C%20MERN%20Stack&descAlignY=60" alt="Project Banner" />
</p>

<p align="center">
  A full-stack electronic voting platform with secure authentication, role-based access, and real-time election management.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/version-1.0.0-blue.svg" alt="Version" />
  <img src="https://img.shields.io/badge/node.js-14%2B-brightgreen.svg" alt="Node" />
  <img src="https://img.shields.io/badge/react-vite-61dafb.svg" alt="React" />
  <img src="https://img.shields.io/badge/database-MongoDB-47A248" alt="MongoDB" />
  <img src="https://img.shields.io/badge/status-active-success" alt="Status" />
  <img src="https://img.shields.io/badge/license-Educational-lightgrey" alt="License" />
</p>

---

## 📌 Quick Navigation

* [🚀 Overview](#-overview)
* [✨ Features](#-features)
* [🧰 Tech Stack](#-tech-stack)
* [📦 Installation](#-installation)
* [⚙️ Configuration](#-configuration)
* [▶️ Usage](#-usage)
* [🖼️ Screenshots / Demo](#screenshots-demo)
* [🔌 API Reference](#-api-reference)
* [📁 Folder Structure](#-folder-structure)
* [🛠️ Troubleshooting](#troubleshooting)
* [🤝 Contributing](#-contributing)

---

## 🚀 Overview

This project is a **full-stack E-Voting System** built using the MERN stack, designed to provide a secure and efficient digital voting experience.

It supports:

* **Role-based authentication** (Admin & Voter)
* **Election lifecycle management**
* **Secure vote casting and result tracking**
* **Protected frontend routes with persistent sessions**

The application combines a **Node.js + Express backend** with a **React (Vite) frontend**, ensuring scalability and responsiveness.

---

## ✨ Features

### Core Capabilities

* **JWT Authentication**: Secure login and session management
* **Role-Based Access Control**: Separate dashboards for Admins and Voters
* **Election Management (Admin)**: Create, update, and delete elections
* **Vote Casting (Voter)**: Participate in elections securely
* **Results Viewing**: Access voting results in real time
* **Protected Routes**: Frontend route protection with persisted auth state
* **RESTful APIs**: Clean and modular backend endpoints

### User Roles

| Role      | Permissions                             |
| --------- | --------------------------------------- |
| **Admin** | Create, update, delete elections        |
| **Voter** | View elections, cast votes, see results |

---

## 🧰 Tech Stack

| Layer             | Technologies              |
| ----------------- | ------------------------- |
| Backend           | Node.js, Express          |
| Database          | MongoDB, Mongoose         |
| Authentication    | JWT (JSON Web Token)      |
| Frontend          | React, Vite, Tailwind CSS |
| API Communication | Axios                     |
| Routing           | React Router              |

---

## 📦 Installation

### Prerequisites

* **Node.js 14+**
* **MongoDB** (local or Atlas)
* **npm** or **yarn**

```bash
node --version
npm --version
```

---

### Step-by-Step Setup

#### 1. Clone the repository

```bash
git clone <repository-url>
cd e-voting-system
```

---

#### 2. Backend Setup

```bash
cd backend
npm install
```

Start the development server:

```bash
npm run dev
```

Backend runs at:
👉 [http://localhost:5000](http://localhost:5000)

---

#### 3. Frontend Setup

```bash
cd frontend
npm install
npm run dev
```

Frontend runs at:
👉 [http://localhost:5173](http://localhost:5173)

---

## ⚙️ Configuration

Create a `.env` file inside the `backend/` directory:

```env
NODE_ENV=development
PORT=5000
MONGO_URI=mongodb://127.0.0.1:27017/eVotingDB
JWT_SECRET=your_jwt_secret
```

### 🔧 Frontend Configuration

* Update API base URL in:

  ```
  frontend/src/api/axios.js
  ```
* Default is set to `http://localhost:5000`

---

## ▶️ Usage

### Start the Application

1. Start MongoDB
2. Run backend server (`npm run dev`)
3. Run frontend (`npm run dev`)

---

### Workflow

1. **Register/Login** as Admin or Voter
2. **Admin**:

   * Create and manage elections
3. **Voter**:

   * View available elections
   * Cast vote securely
4. **Results**:

   * View election outcomes

---

<a id="screenshots-demo"></a>

## 🖼️ Screenshots / Demo

> No screenshots or live demo link provided.

* Demo URL: **[Add deployment link here]**
* Suggested Screens:

  * Login/Register Page
  * Admin Dashboard
  * Election Management Panel
  * Voting Interface
  * Results Dashboard

---

## 🔌 API Reference

### Base URL

```bash
http://localhost:5000
```

### Core Endpoints

| Endpoint             | Method | Description             |
| -------------------- | ------ | ----------------------- |
| `/api/auth/register` | POST   | Register user           |
| `/api/auth/login`    | POST   | Login user              |
| `/api/elections`     | GET    | Get all elections       |
| `/api/elections/:id` | GET    | Get single election     |
| `/api/elections`     | POST   | Create election (Admin) |
| `/api/elections/:id` | PUT    | Update election         |
| `/api/elections/:id` | DELETE | Delete election         |
| `/api/votes`         | POST   | Cast vote               |
| `/api/votes`         | GET    | Get voting results      |

---

<details>
<summary><strong>Request Examples</strong></summary>

### Register

```http
POST /api/auth/register
Content-Type: application/json

{
  "email": "user@example.com",
  "password": "password"
}
```

---

### Login

```http
POST /api/auth/login
Content-Type: application/json

{
  "email": "user@example.com",
  "password": "password"
}
```

---

### Create Election (Admin)

```http
POST /api/elections
Authorization: Bearer <token>
Content-Type: application/json
```

---

### Cast Vote

```http
POST /api/votes
Authorization: Bearer <token>
Content-Type: application/json
```

</details>

---

## 📁 Folder Structure

```text
e-voting-system/
├── backend/
│   ├── config/
│   ├── models/
│   ├── routes/
│   ├── controllers/
│   ├── middleware/
│   └── server.js
│
├── frontend/
│   ├── src/
│   ├── components/
│   ├── pages/
│   └── api/
│
└── README.md
```

---

<a id="troubleshooting"></a>

## 🛠️ Troubleshooting

<details>
<summary><strong>Backend Issues</strong></summary>

**MongoDB connection failed**

* Ensure MongoDB is running
* Verify `MONGO_URI` in `.env`

**JWT errors**

* Check `JWT_SECRET` value
* Ensure token is sent in headers

</details>

---

<details>
<summary><strong>Frontend Issues</strong></summary>

**API not connecting**

* Verify backend is running on port 5000
* Check Axios base URL

**Auth not persisting**

* Check localStorage handling in auth context

</details>

---

## 🤝 Contributing

Contributions are welcome to improve this project.

1. Fork the repository
2. Create a new branch
3. Make your changes
4. Submit a pull request

---

## 👨‍💻 Author

**Bibek Samantray**

AI/ML Enthusiast | Full-Stack Developer

[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/bibeksamantray)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/bibek-samantray)

---

<div align="center">

### ⭐ Star this repo if you find it useful!

Secure voting built with 🗳️ and modern web technologies

</div>
