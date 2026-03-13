# E-Blog - Full-Stack Blogging Platform

[![Backend](https://img.shields.io/badge/Backend-Node.js%20%7C%20Express%20%7C%20MongoDB-green)](https://nodejs.org)
[![Frontend](https://img.shields.io/badge/Frontend-React%20%7C%20Vite%20%7C%20Tailwind-blue)](https://reactjs.org)
[![Dark Mode](https://img.shields.io/badge/Dark%20Mode-Supported-%230d1117)](https://reactjs.org)

E-Blog is a modern, full-stack blogging platform built with the MERN stack (MongoDB, Express.js, React, Node.js). It features rich text editing, image uploads, user authentication (including Google OAuth), a comprehensive admin panel, real-time comments, and a responsive dark/light theme UI.

## ✨ Features

### User Features
- **User Authentication**: Email/password signup/login + Google OAuth sign-in
- **Profile Management**: Edit username, email, job title, upload profile picture
- **Rich Blog Creation**: Create blogs with TinyMCE rich text editor, image upload (drag & drop), categories
- **Blog Browsing**: Filter blogs by category, responsive card layouts, hover animations
- **Blog Reading**: Full-screen hero layouts, rich content rendering, social sharing
- **Interactive Comments**: Post/delete comments on blogs (real-time updates)
- **Responsive Design**: Mobile-first, dark/light theme toggle
- **Modern UI/UX**: Tailwind CSS, Framer Motion animations, toast notifications

### Admin Features (admin@gmail.com / admin)
- **User Management**: View all users, delete users (except admin)
- **Content Moderation**: Delete blogs and comments
- **Full CRUD**: Complete control over blogs (create/update/delete)

### Guest Features
- Browse all blogs
- Read blog posts with comments
- Landing page with platform showcase

### Technical Features
- **File Uploads**: Multer for secure image uploads (blogs & profiles), static serving
- **JWT Authentication**: Secure token-based auth with refresh
- **Database**: MongoDB with Mongoose ODM (User, Blog, Comment models)
- **API Security**: Auth middleware, role-based access (admin only routes)
- **Performance**: Optimized image handling, pagination-ready
- **Modern Stack**: ES6+ modules, async/await, React hooks/Context

## 🛠 Tech Stack

| Category | Technologies |
|----------|--------------|
| **Backend** | Node.js, Express.js, MongoDB, Mongoose, JWT, bcryptjs, Multer |
| **Frontend** | React 18, Vite, Tailwind CSS, React Router, TinyMCE, Framer Motion |
| **Auth** | JWT, Google OAuth (@react-oauth/google) |
| **UI/UX** | React Icons, React Toastify, Heroicons |
| **Dev Tools** | ESLint, Prettier, dotenv |
| **Other** | CORS, Nodemon, Firebase (SDK included) |

## 📁 Project Structure

```
E-Blog/
├── E-Blog_back/           # Node.js/Express API
│   ├── controllers/        # Business logic (auth, blog, comment)
│   ├── models/            # Mongoose schemas (User, Blog, Comment)
│   ├── middleware/        # Auth & admin middleware
│   ├── routes/            # API routes
│   ├── db/                # MongoDB connection
│   ├── uploads/           # Static images/profiles
│   └── index.js           # Server entry
├── E-Blog_front/          # React/Vite SPA
│   ├── src/
│   │   ├── Components/    # Reusable UI (Navbar, BlogCard, etc.)
│   │   ├── Pages/         # Page components
│   │   ├── Admin/         # Admin dashboard
│   │   ├── contexts/      # ThemeContext
│   │   └── assets/        # Images & logos
│   ├── public/            # Static assets
│   └── vite.config.js     # Vite + Tailwind config
└── README.md              # This file
```

## 🚀 Quick Start

### Prerequisites
- Node.js (18+)
- MongoDB (local or Atlas)
- npm/yarn/pnpm

### Backend Setup
```bash
cd E-Blog_back
cp .env.example .env  # Create .env
# Edit .env: MONGODB_URL, JWT_SECRET, PORT=4000
npm install
npm run start  # or nodemon index.js
```
Server runs at `http://localhost:4000`

### Frontend Setup
```bash
cd E-Blog_front
npm install
npm run dev
```
App runs at `http://localhost:5173` (Vite default)

### Environment Variables (.env)
```
PORT=4000
MONGODB_URL=mongodb://localhost:27017/eblog  # or MongoDB Atlas URL
JWT_SECRET=your-super-secret-jwt-key
```

### Admin Login
```
Email: admin@gmail.com
Password: admin
```

## 🌐 API Endpoints

| Method | Endpoint | Auth | Description |
|--------|----------|------|-------------|
| POST | `/signup` | - | Create user account |
| POST | `/login` | - | User login |
| POST | `/google-signin` | - | Google OAuth |
| PUT | `/users/profile` | ✅ | Update profile + image |
| GET | `/users` | Admin | List users |
| DELETE | `/users/:id` | Admin | Delete user |
| POST | `/blogs` | ✅ | Create blog + image |
| GET | `/blogs` | - | List all blogs |
| GET | `/blogs/:id` | - | Single blog |
| DELETE | `/blogs/:id` | Admin | Delete blog |
| PUT | `/blogs/:id` | Admin | Update blog |
| POST | `/comments` | ✅ | Add comment |
| GET | `/comments/:blogId` | - | Blog comments |
| GET | `/comments/all` | ✅ | All comments |
| DELETE | `/comments/:id` | ✅ | Delete comment |

Static files: `/uploads/*`

## 📱 Screenshots

Add screenshots here:
- ### Landing page
  <img width="560" height="350" alt="Screenshot 2026-03-13 115234" src="https://github.com/user-attachments/assets/cb1b9961-7d30-43a1-b4ea-f7811cb7c5a2" />
- ### Blog listing
  <img width="560" height="350" alt="Screenshot 2026-03-13 120319" src="https://github.com/user-attachments/assets/59a1b93b-7092-4170-8a8d-4c32f91a2158" />
- ### Blog post view
  <img width="560" height="350" alt="Screenshot 2026-03-13 120428" src="https://github.com/user-attachments/assets/3b6ee4d9-6a1b-4a4b-8fab-0dab3462f5ed" />
- ### Create blog (TinyMCE)
  <img width="560" height="350" alt="Screenshot 2026-03-13 120507" src="https://github.com/user-attachments/assets/be4895e0-5845-45d5-9b3d-d8796c002e51" />
- ### Admin dashboard
  - Main Dashboard
   <br><img width="560" height="350" alt="Screenshot 2026-03-13 120852" src="https://github.com/user-attachments/assets/0ea086b6-0d24-4420-87c1-2a2c9eba3f5e" />
  - User Panel
    <br><img width="560" height="350" alt="Screenshot 2026-03-13 120922" src="https://github.com/user-attachments/assets/85b65ed0-4c7a-481e-9ccd-491f9e351b45" />
  - Blog Panel
    <br><img width="560" height="350" alt="Screenshot 2026-03-13 120937" src="https://github.com/user-attachments/assets/3eb87f03-3185-4eec-84d4-359ffaa8ad79" />
  - Comments Panel
    <br><img width="560" height="350" alt="Screenshot 2026-03-13 120947" src="https://github.com/user-attachments/assets/e462f80e-11a8-44c0-a432-6dbcafa6f1a7" />




  

