# MERN Movies App

A movie catalogue built with the MERN stack: browse and search movies, register and log in, leave reviews, and manage content through an admin panel.

## Tech stack

- **Frontend:** React 18, Vite, React Router 6, Redux Toolkit (RTK Query), Tailwind CSS, react-slick, react-toastify
- **Backend:** Node.js, Express 4
- **Database:** MongoDB with Mongoose
- **Auth:** JWT in an httpOnly cookie, bcryptjs password hashing
- **Uploads:** multer (local `uploads/` folder)

## Features

- Home page with new, top and random movie sliders and a genre filter
- Browse page with search, genre, year and sort options
- Movie details with cast and user reviews
- Register, login, logout and profile editing
- Admin panel: dashboard, create and edit movies (with image upload), manage genres, moderate comments

## Project structure

```
backend/    Express API (routes, controllers, models, middlewares)
frontend/   React app (Vite)
uploads/    Uploaded movie images (git-ignored)
```

## Getting started

### Prerequisites
- Node.js 18+
- A MongoDB database (local or MongoDB Atlas)

### Setup

```bash
# 1. Install dependencies
npm install
cd frontend && npm install && cd ..

# 2. Create your environment file
cp .env.example .env
# then edit .env and set MONGO_URI and JWT_SECRET

# 3. Run backend and frontend together
npm run fullstack
```

- Backend: http://localhost:3000
- Frontend: http://localhost:5173 (proxies `/api` and `/uploads` to the backend)

### Making an admin user

New users are not admins. Register an account, then set `isAdmin: true` on that user in your MongoDB database (Atlas UI or Compass) to access the admin panel.

## API overview

| Area | Base path |
|---|---|
| Users | `/api/v1/users` |
| Genres | `/api/v1/genre` |
| Movies | `/api/v1/movies` |
| Upload | `/api/v1/upload` |

## Scripts

| Command | What it does |
|---|---|
| `npm run fullstack` | Runs backend and frontend together |
| `npm run backend` | Runs the API with nodemon |
| `npm run frontend` | Runs the Vite dev server |
