# SIT Sec-B Student Information & Academic Portal (CA-03)

[![Node.js](https://img.shields.io/badge/Node.js-v24.22-green)](https://nodejs.org/)
[![Express](https://img.shields.io/badge/Express-v5.2-blue)](https://expressjs.com/)
[![MongoDB](https://img.shields.io/badge/MongoDB-v9.0-emerald)](https://www.mongodb.com/)
[![React](https://img.shields.io/badge/React-v19.2-cyan)](https://react.dev/)
[![Vite](https://img.shields.io/badge/Vite-v8.3-purple)](https://vitejs.dev/)

A full-stack Student Academic Portal developed for **Continuous Assessment 03 (CA-03)**, based on the repository [somesh-chutel/25070521060-CA-03](https://github.com/somesh-chutel/25070521060-CA-03.git) by **Prof. Somesh Chutel**.

---

## 🌟 Overview & Features

- **Full-Stack Architecture**: Modern React 19 + Vite frontend paired with an Express 5 RESTful API and MongoDB database.
- **Complete MongoDB Integration**: Native MongoDB driver connection to database `sitSecB` and collection `student`, fully inspectable via MongoDB Compass.
- **Robust CRUD Operations**:
  - `GET /getall`: Retrieve all enrolled students
  - `GET /get/:id`: Retrieve student by MongoDB `ObjectId`
  - `POST /create`: Register new student with bcrypt encrypted password
  - `POST /login`: Authenticate student and issue signed JWT token
  - `PUT /update/:id`: Update student status, age, name, and email
  - `DELETE /delete/:id`: Delete student record from MongoDB
- **Security**:
  - `bcrypt`: 10-round salted password hashing
  - `jsonwebtoken`: Role-based payload generation with `subject` and `role`
  - `cors`: Cross-Origin Resource Sharing enabled for seamless client communication
- **Frontend Experience**:
  - **Home / Dashboard**: Real-time KPI metrics, search by name/email, status filtering, Table View and Grid View switcher.
  - **Modals**: Add Student, Edit Record, View Profile Card, and Delete Confirmation.
  - **About Page**: Technical documentation, system architecture data flow, and academic credits.
  - **Services Page**: Roster Export (JSON / CSV), live in-browser REST API tester tool.
  - **Contact Page**: Interactive inquiry form with validation, faculty contacts, and lab guidelines.
  - **Auth Portal**: Dedicated Login and Register views with persistent JWT session state.
  - **Graceful Fallback**: In addition to native MongoDB connection, provides an in-memory fallback so the application is completely testable and resilient even when the MongoDB daemon is offline.

---

## 📁 Project Structure

```
d:\flexi\
├── package.json             # Root workspace runner scripts
├── README.md                # Comprehensive documentation
├── server\                  # Backend (Node.js + Express + MongoDB)
│   ├── server.js            # Express API server with MongoDB & JWT
│   ├── test_unit.js         # Automated endpoint verification suite
│   ├── package.json         # Server dependencies & scripts
│   └── node_modules\        # Pre-installed dependencies
└── client\                  # Frontend (React 19 + Vite + CSS)
    ├── index.html           # HTML template with Google Fonts & Bootstrap
    ├── vite.config.js       # Vite configuration with API proxy
    ├── package.json         # Client dependencies & scripts
    └── src\
        ├── main.jsx         # React application entry point with BrowserRouter
        ├── App.jsx          # Root component & Route definitions
        ├── index.css        # Theme variables, badges, buttons, cards & modals
        ├── App.css          # Navigation, hero, responsive tables & footer styles
        ├── nav.jsx          # Sticky navbar with live MongoDB status indicator
        ├── home.jsx         # Interactive Student Management Dashboard
        ├── about.jsx        # Architecture overview & academic credits
        ├── services.jsx     # Data export tools (JSON/CSV) & API Tester
        ├── contact.jsx      # Academic inquiry form & faculty details
        ├── context\
        │   └── AuthContext.jsx  # Global auth state & MongoDB health polling
        ├── services\
        │   └── api.js       # Centralized REST client with proxy fallback
        ├── components\
        │   └── StudentModals.jsx # Add, Edit, View, and Delete modals
        └── homeComp\
            ├── header.jsx   # Hero banner with call-to-actions
            ├── footer.jsx   # Academic credits and institutional footer
            └── mainContentCont.jsx # Real-time statistics counter cards
```

---

## 🚀 Getting Started

### 1. Prerequisites
- **Node.js** (v18 or higher; v24 recommended)
- **MongoDB Server / MongoDB Compass** (listening on `mongodb://127.0.0.1:27017`)

### 2. Start the MongoDB Server
If using MongoDB Compass, connect to:
```
mongodb://localhost:27017
```
Or start MongoDB Server locally:
```powershell
& "C:\Program Files\MongoDB\Server\9.0\bin\mongod.exe" --dbpath "C:\Program Files\MongoDB\Server\9.0\data"
```

### 3. Start Backend Server
```powershell
cd d:\flexi\server
node server.js
```
The server will start at `http://localhost:5000` and automatically connect to MongoDB database `sitSecB`.

### 4. Run Automated Backend Tests
To verify all 7 endpoints (`/getall`, `/get/:id`, `/create`, `/login`, `/update/:id`, `/delete/:id`, `/api/health`):
```powershell
cd d:\flexi\server
npm test
```

### 5. Start Frontend Client
In a separate terminal:
```powershell
cd d:\flexi\client
npm run dev
```
Open your browser at `http://localhost:5173`.

---

## 🔑 Default Credentials for Testing

| Email | Password | Role / Status |
|---|---|---|
| `aarav.sharma@sit.edu` | `password123` | Active |
| `diya.patel@sit.edu` | `password123` | Active |
| `rohan.verma@sit.edu` | `password123` | Graduated |
| `ananya.iyer@sit.edu` | `password123` | Inactive |

---

## 👨‍🏫 Academic Information
- **Institution**: Symbiosis Institute of Technology (SIT)
- **Section**: Sec-B
- **Assessment**: Continuous Assessment 03 (CA-03)
- **Faculty Mentor**: Prof. Somesh Chutel ([GitHub](https://github.com/somesh-chutel))
- **Base Repository**: `somesh-chutel/25070521060-CA-03`
