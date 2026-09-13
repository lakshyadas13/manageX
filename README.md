# 📋 ManageX

> A modern, full-stack task management application with seamless authentication, multi-user collaboration, and intuitive user experience

[![Live Demo](https://img.shields.io/badge/Live%20Demo-ManageX-blue?style=for-the-badge)](https://manage-x-frontend.vercel.app)
[![License](https://img.shields.io/badge/LICENSE-MIT-6B8E23?style=for-the-badge)](LICENSE)

---

## 🎯 Overview

**ManageX** is a professional task management web application designed to help teams and individuals organize, prioritize, and track their work effortlessly. With a clean, modern UI inspired by Notion, it combines powerful task management features with robust backend infrastructure for a seamless experience.

---

## ✨ Features

- ✅ **Authentication**: Secure JWT-based login and registration with password hashing (bcryptjs)
- 📝 **Task CRUD Operations**: Create, read, update, and delete tasks with ease
- 🎯 **Priority Levels**: Organize tasks by priority (Low, Medium, High)
- 🏷️ **Task Tags**: Categorize tasks with custom tags for better organization
- 📅 **Due Dates & Times**: Set deadlines with precise date and time tracking
- 📌 **Task Notes**: Add detailed notes and descriptions to each task
- 🔍 **Advanced Filtering**: Compact popover to filter and sort tasks by priority, status, tags, and due dates
- 👥 **Multiple Collaborators**: Assign and collaborate with multiple team members per task using a searchable multi-user picker with smart viewport drop-up/down positioning and compact avatar chips (`👤 👤 +N`)
- 💬 **Task Comments**: Threaded discussion section inside each task with relative timestamps, author avatars, and author-only edit/delete permissions
- 📜 **Task Activity History**: Reverse-chronological timeline tracking key events (task creation, status toggles, priority changes, due date updates, collaborator additions/removals, and comments)
- 📑 **Task Details Modal**: Dedicated tabbed view (`[ Details ]`, `[ Comments ]`, `[ Activity ]`) accessible from each card for focused task interaction
- ⚡ **Compact Action Toolbar**: Clean top-right icon buttons with accessible tooltips (`View Details` info icon, `Add to Calendar`, `Mark Complete/Pending`, `Edit`, `Delete` with subtle destructive hover)
- 📊 **Progress Dashboard & Analytics**: GitHub-style contribution activity grid tracking completed tasks day-by-day
- 👤 **Profile & Productivity Hub**: Account drawer to view profile details, securely change passwords, track completion progress, and export weekly summaries
- 🌤️ **Dashboard Widgets**: Dynamic real-time weather (powered by browser geolocation with fallback city) and daily motivational quotes
- 🗓️ **Calendar Sync**: One-click functionality to instantly add tasks and reminders directly to Google Calendar
- 🔔 **Smart Alert System**: Proactive, context-aware notification banners dynamically warning you of high priorities and rapidly approaching deadlines
- 📄 **Task Report Exports**: Seamless client-side functionality to generate and download categorized weekly PDF activity summaries (powered by jsPDF)
- 📱 **Fully Responsive**: Optimized for desktop, tablet, and mobile devices
- 🎨 **Modern UI/UX**: Clean, intuitive interface with smooth transitions, subtle shaders, and pure Lucide React iconography (zero emojis)

---

## 🛠️ Tech Stack

### Frontend
- **React 18** - UI library
- **TypeScript** - Type-safe development
- **Vite** - Lightning-fast build tool
- **Tailwind CSS** - Utility-first styling
- **Lucide React** - Beautiful, consistent icon set
- **Framer Motion & Shaders** - Subtle micro-animations and visual styling
- **jsPDF** - Client-side PDF report generation

### Backend
- **Node.js** - JavaScript runtime
- **Express.js** - Web framework
- **JWT & bcryptjs** - Authentication & security
- **Mongoose 8** - MongoDB ODM with schema validation & modeling

### Database
- **MongoDB Atlas** - Cloud database

### External APIs
- **WeatherAPI** - Real-time weather forecasting by coordinates and city
- **ZenQuotes API** - Daily motivational quotes with resilient fallbacks

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

| Profile | Login |
|-----------|-----------|
| ![Profile](assets/screenshots/profile.png) | ![Login](assets/screenshots/login-page.png) |

---

## 🔗 Repository Links

- 🎨 **Frontend Repository**: [ManageX-Frontend](https://github.com/lakshyadas13/manageX_frontend.git)
- ⚙️ **Backend Repository**: [ManageX-Backend](https://github.com/lakshyadas13/manageX_backend.git)

---

## 🚀 Setup Instructions

### Prerequisites
- Node.js (v18 or higher)
- npm or yarn
- MongoDB Account (MongoDB Atlas)

### 1. Clone Repositories

```bash
# Clone frontend
git clone https://github.com/lakshyadas13/manageX_frontend.git
cd manageX_frontend

# Clone backend
cd ..
git clone https://github.com/lakshyadas13/manageX_backend.git
cd manageX_backend
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
PORT=5001
MONGO_URI=mongodb+srv://username:password@cluster.mongodb.net/managex
JWT_SECRET=your_super_secret_jwt_key_here_change_in_production
JWT_EXPIRES_IN=7d
WEATHER_API_KEY=your_weatherapi_key_here
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
VITE_API_BASE_URL=http://localhost:5001
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
- 🔌 Backend API: `http://localhost:5001`

---

## 🔌 API Endpoints

### Authentication
- `POST /auth/register` - Register a new user and receive JWT
- `POST /auth/login` - Login user and receive JWT
- `GET /health` - Health check

### Users & Account
- `GET /api/users` - Fetch all users for collaborator search (auth required)
- `PATCH /api/users/change-password` - Update account password (auth required)

### Tasks & Collaboration
- `POST /tasks` - Create a task with optional `collaborators` (auth required)
- `GET /tasks` - Fetch tasks visible to user (owned, assigned, collaborated) with filters/sort (auth required)
- `GET /tasks/:id` - Fetch single task details with populated users (auth required)
- `PUT /tasks/:id` - Update task (creator: full; collaborator: completion status) (auth required)
- `PATCH /tasks/:id` - Partial task update (auth required)
- `PATCH /tasks/:id/collaborators` - Manage task collaborators (creator only)
- `DELETE /tasks/:id` - Delete task and cascade delete comments/activity (creator only)

### Task Comments
- `GET /tasks/:taskId/comments` - List comments for a task in chronological order (auth required)
- `POST /tasks/:taskId/comments` - Post a comment and log activity (auth required)
- `PATCH /comments/:commentId` - Edit own comment (author only)
- `DELETE /comments/:commentId` - Delete own comment (author only)

### Task Activity History
- `GET /tasks/:taskId/activity` - Fetch reverse-chronological activity history for a task (auth required)

### External Integrations
- `GET /api/weather` - Live weather data by coordinates (`?lat=...&lon=...`) or city (`?city=...`)
- `GET /api/quotes/random` - Daily motivational quotes with built-in fallbacks

For protected routes, include header:

```http
Authorization: Bearer <token>
```

### Query Params for `GET /tasks`
- `priority=low|medium|high`
- `completed=true|false`
- `tags=work,urgent`
- `sort=dueDateAsc|dueDateDesc|priorityHigh|priorityLow|createdAtDesc|createdAtAsc`

---

## 🐛 Challenges Faced & Solutions

| Challenge | Solution |
|-----------|----------|
| **MongoDB Connection Issues** | Implemented connection retry logic and improved error handling with clear error messages |
| **CORS Errors** | Configured CORS middleware properly in Express with specific origin whitelisting |
| **JWT Token Validation** | Created middleware to validate tokens on protected routes and handle token expiration |
| **Environment Variable Management** | Used dotenv package with validation to ensure required variables are set |
| **Multi-Collaborator Backwards Compatibility** | Preserved `assignedTo` alongside `collaborators` array with automatic bidirectional synchronization |
| **Comment & Activity Authorization** | Implemented role-based checks ensuring only authors can edit/delete comments and non-creators can only toggle completion status |
| **Mobile Responsiveness & Viewport Clipping** | Implemented smart viewport detection to auto-flip dropdowns upward when near the screen bottom |

---

## 🎨 Future Improvements

- [x] 👥 **Team Collaboration** - Multiple collaborators, role-based permissions, and task discussions *(Implemented)*
- [x] 💬 **Task Discussions** - In-task comments with author editing/deletion *(Implemented)*
- [x] 📜 **Activity Timeline** - Full audit trail of task changes and updates *(Implemented)*
- [x] 📤 **Export Features** - Export tasks to weekly PDF reports and Google Calendar *(Implemented)*
- [x] 📊 **Productivity Analytics** - GitHub-style contribution grid & completion analytics *(Implemented)*
- [ ] 🔔 **Push Notifications** - Browser push notifications and deadline reminders
- [ ] 🌙 **Dark Mode** - Full dark theme toggle
- [ ] 📱 **Mobile Applications** - Native iOS and Android apps using React Native
- [ ] 🔄 **Recurring Tasks** - Support for repeating tasks with customizable intervals
- [ ] 🤖 **AI Integration** - Smart task breakdown and automated categorization
- [ ] 🔐 **Two-Factor Authentication** - Enhanced security with 2FA support

---

## 🚀 Deployment Guide

### Frontend on Vercel

1. Push project to GitHub.
2. In Vercel, import the `manageX_frontend` repository.
3. Build command: `npm run build`
4. Output directory: `dist`
5. Add environment variable:
   ```env
   VITE_API_BASE_URL=https://<your-backend-domain>
   ```
6. Deploy.

### Backend on Render / Railway

1. Create a new Web Service from the `manageX_backend` repository.
2. Add environment variables:
   ```env
   PORT=5001
   MONGO_URI=<your-mongodb-connection-string>
   CORS_ORIGIN=https://<your-vercel-frontend-domain>
   JWT_SECRET=<your-strong-secret>
   JWT_EXPIRES_IN=7d
   WEATHER_API_KEY=<your-weather-api-key>
   ```
3. Start command: `npm start`
4. Deploy and set the backend URL in Vercel.

---

## 📜 Available Scripts

**Backend:**
- `npm run dev` - Start backend with nodemon
- `npm start` - Start backend server in production

**Frontend:**
- `npm run dev` - Start Vite dev server
- `npm run build` - Production bundle build
- `npm run preview` - Preview production build
- `npm run typecheck` - TypeScript checks

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 👨‍💻 Author

**Lakshya Das**  
- 🔗 GitHub: [@lakshyadas13](https://github.com/lakshyadas13)
- 💼 LinkedIn: [Lakshya Das](https://linkedin.com/in/lakshyadas)
