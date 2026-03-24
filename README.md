# 📋 ManageX

> A modern, full-stack task management application with seamless authentication and intuitive user experience

[![Demo](https://img.shields.io/badge/Live%20Demo-Coming%20Soon-blue)](.)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

---

## 🎯 Overview

**ManageX** is a professional task management web application designed to help teams and individuals organize, prioritize, and track their work effortlessly. With a clean, modern UI inspired by Notion, it combines powerful task management features with robust backend infrastructure for a seamless experience.

---

## ✨ Features

- ✅ **Authentication**: Secure JWT-based login and registration with password hashing (bcryptjs)
- 📝 **Task CRUD Operations**: Create, read, update, and delete tasks with ease
- 🎯 **Priority Levels**: Organize tasks by priority (Low, Medium, High, Critical)
- 🏷️ **Task Tags**: Categorize tasks with custom tags for better organization
- 📅 **Due Dates & Times**: Set deadlines with precise date and time tracking
- 📌 **Task Notes**: Add detailed notes and descriptions to each task
- 🔍 **Advanced Filtering**: Filter and sort tasks by priority, status, and more
- 📊 **Progress Dashboard**: Visualize task completion with contribution-style heatmap analytics
- 📱 **Fully Responsive**: Optimized for desktop, tablet, and mobile devices
- 🎨 **Modern UI/UX**: Clean, intuitive interface for optimal user experience

---

## 🛠️ Tech Stack

### Frontend
- **React 18** - UI library
- **TypeScript** - Type-safe development
- **Vite** - Lightning-fast build tool
- **Tailwind CSS** - Utility-first styling
- **Lucide React** - Beautiful icon set

### Backend
- **Node.js** - JavaScript runtime
- **Express.js** - Web framework
- **JWT & bcryptjs** - Authentication & security
- **Mongoose** - MongoDB ODM

### Database
- **MongoDB Atlas** - Cloud database
- **Mongoose 8** - Schema validation & modeling

---

## 🏗️ System Architecture

```
┌─────────────────────────────────────────────────────────┐
│                    ManageX Application                  │
├─────────────────────────────────────────────────────────┤
│                                                         │
│  ┌──────────────────┐           ┌──────────────────┐    │
│  │  React Frontend  │           │  Express Backend │    │
│  │  (Vite + Tail)   │◄─────────►│    (REST API)    │    │
│  │                  │    HTTP   │                  │    │
│  └──────────────────┘           └──────────────────┘    │
│         │                               │               │
│         │ Auth Token (JWT)              │ Routes        │
│         │                               │               │
│         └───────────────────────────────┤               │
│                                         │               │
│                            ┌─────────────────────┐      │
│                            │   MongoDB Atlas     │      │
│                            │   (Database Layer)  │      │
│                            └─────────────────────┘      │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

---

## 📸 Screenshots

| Dashboard | Task Form |
|-----------|-----------|
| ![Dashboard](assets/screenshots/dashboard.png) | ![Task Form](assets/screenshots/task-form.png) |

| Progress Heatmap | Login |
|------------------|-------|
| ![Progress Heatmap](assets/screenshots/progress-heatmap.png) | ![Login](assets/screenshots/login-page.png) |

---

## 🔗 Repository Links

- 🎨 **Frontend Repository**: [ManageX-Frontend](https://github.com/lakshyadas13/manageX_frontend.git)
- ⚙️ **Backend Repository**: [ManageX-Backend](https://github.com/lakshyadas13/manageX_backend.git)

---

## 🚀 Setup Instructions

### Prerequisites
- Node.js (v16 or higher)
- npm or yarn
- MongoDB Account (MongoDB Atlas)

### 1. Clone Repositories

```bash
# Clone frontend
git clone https://github.com/lakshyadas13/managex-frontend.git
cd managex-frontend

# Clone backend
cd ..
git clone https://github.com/lakshyadas13/managex-backend.git
cd managex-backend
```

### 2. Backend Setup

```bash
cd backend

# Install dependencies
npm install

# Configure environment variables
cp .env.example .env
```

Edit `backend/.env`:

```env
PORT=5000
MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/managex
JWT_SECRET=your_super_secret_jwt_key_here_change_in_production
JWT_EXPIRES_IN=7d
NODE_ENV=development
```

### 3. Frontend Setup

```bash
cd ../frontend

# Install dependencies
npm install

# Configure environment variables
cp .env.example .env
```

Edit `frontend/.env`:

```env
VITE_API_URL=http://localhost:5000
VITE_APP_NAME=ManageX
```

### 4. Run the Application

**Terminal 1 - Backend:**
```bash
cd backend
npm run dev
```

**Terminal 2 - Frontend:**
```bash
cd frontend
npm run dev
```

**Access the application:**
- 🌐 Frontend: `http://localhost:5173`
- 🔌 Backend API: `http://localhost:5000`

---

## 🐛 Challenges Faced

| Challenge | Solution |
|-----------|----------|
| **MongoDB Connection Issues** | Implemented connection retry logic and improved error handling with clear error messages |
| **CORS Errors** | Configured CORS middleware properly in Express with specific origin whitelisting |
| **JWT Token Validation** | Created middleware to validate tokens on protected routes and handle token expiration |
| **Environment Variable Management** | Used dotenv package with validation to ensure required variables are set |
| **State Management Complexity** | Implemented Context API for efficient state management across the app |
| **Mobile Responsiveness** | Used Tailwind CSS responsive utilities and mobile-first design approach |

---

## 🎨 Future Improvements

- 📊 **Advanced Analytics Dashboard** - Detailed insights into task completion rates and productivity metrics
- 🌙 **Dark Mode** - Complete dark theme implementation
- 📱 **Mobile Applications** - Native iOS and Android apps using React Native
- 👥 **Team Collaboration** - Real-time task sharing and team management features
- 🔔 **Push Notifications** - Task reminders and deadline alerts
- 🗂️ **Project Management** - Organize tasks into projects with team workspaces
- 🔄 **Recurring Tasks** - Support for repeating tasks with customizable intervals
- 📤 **Export Features** - Export tasks to PDF, CSV, or calendar formats
- 🤖 **AI Integration** - Smart task suggestions and automated categorization
- 🔐 **Two-Factor Authentication** - Enhanced security with 2FA support

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 👨‍💻 Author

**Lakshya Das**  
- 🔗 GitHub: [@lakshyadas13](https://github.com/lakshyadas13)
- 💼 LinkedIn: [Lakshya Das](https://linkedin.com/in/lakshyadas)

---

## API Endpoints

- `POST /auth/register` - Register a new user and receive JWT
- `POST /auth/login` - Login user and receive JWT
- `GET /health` - Health check

- `POST /tasks` - Create a task (auth required)
- `GET /tasks` - Fetch tasks with optional filters/sort (auth required)
- `PUT /tasks/:id` - Update a task (auth required)
- `DELETE /tasks/:id` - Delete a task (auth required)

For protected task routes, include header:

```http
Authorization: Bearer <token>
```

### Query Params for `GET /tasks`

- `priority=low|medium|high`
- `completed=true|false`
- `tags=work,urgent`
- `sort=dueDateAsc|dueDateDesc|priorityHigh|priorityLow|createdAtDesc|createdAtAsc`

## Deployment Guide

### Frontend on Vercel

1. Push project to GitHub.
2. In Vercel, import the repository.
3. Set Root Directory to `frontend`.
4. Build command: `npm run build`
5. Output directory: `dist`
6. Add environment variable:

```env
VITE_API_URL=https://<your-railway-backend-domain>
```

7. Deploy.

### Backend on Railway

1. Create a new Railway project from the same GitHub repo.
2. Set Root Directory to `backend`.
3. Add environment variables:

```env
PORT=5000
MONGODB_URI=<your-mongodb-connection-string>
CORS_ORIGIN=https://<your-vercel-frontend-domain>
```

4. Deploy and copy your public backend URL.
5. Update `VITE_API_URL` in Vercel to point to this Railway URL.


## Available Scripts

Backend:

- `npm run dev` - Start backend with nodemon
- `npm start` - Start backend server

Frontend:

- `npm run dev` - Start Vite dev server
- `npm run build` - Production build
- `npm run preview` - Preview production build
- `npm run typecheck` - TypeScript checks
