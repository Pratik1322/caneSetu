# Sugarcane Platform

A full-stack web platform connecting Farmers, Hub Head Managers (HHMs), Workers, and Factories in the sugarcane ecosystem.

## Overview

This project consists of:
- **Frontend**: React 19 + Vite + Tailwind CSS
- **Backend**: Node.js + Express 5 + MongoDB
- **Features**: Role-based access, crop listings, contracts, orders, analytics, and notifications

## Features

- **User Roles**: Farmer, HHM, Worker, Factory with role-based workflows
- **Core Features**: 
  - JWT authentication and role-based access control
  - User profile management
  - Crop listings and order management
  - HHM-worker hiring and invitations
  - Factory partnerships and contracts
  - Analytics dashboard

## Tech Stack

**Backend:**
- Node.js + Express 5
- MongoDB + Mongoose
- JWT authentication
- bcryptjs for password hashing

**Frontend:**
- React 19
- Vite 7
- Tailwind CSS 4
- React Router DOM 7
- Axios

## Prerequisites

- Node.js 18+
- npm 9+
- MongoDB (local or MongoDB Atlas)

## Installation

Clone the repository and install dependencies:

```bash
# Backend
cd backend
npm install

# Frontend
cd frontend
npm install
```

## Configuration

Create `backend/.env`:

```env
PORT=5000
NODE_ENV=development
MONGO_URI=mongodb://localhost:27017/sugarcane-platform
JWT_SECRET=your-secure-secret-key
JWT_EXPIRE=30d
CORS_ORIGIN=http://localhost:5173
```

## Quick Start

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

Default URLs:
- Frontend: http://localhost:5173
- Backend: http://localhost:5000
- Health Check: http://localhost:5000/api/health

## Available Scripts

**Backend:**
- `npm run dev` - Start dev server with nodemon
- `npm start` - Start production server
- `npm test` - Run tests
- `npm run data:import` - Seed database
- `npm run data:destroy` - Clear database

**Frontend:**
- `npm run dev` - Start dev server
- `npm run build` - Build for production
- `npm run lint` - Run ESLint
- `npm run preview` - Preview production build

## Project Structure

```
├── backend/
│   ├── config/          # Database configuration
│   ├── controllers/     # Route controllers
│   ├── middleware/      # Auth & upload middleware
│   ├── models/          # Mongoose schemas
│   ├── routes/          # API routes
│   ├── test_scripts/    # Testing scripts
│   └── server.js        # Express app
├── frontend/
│   ├── public/          # Static assets
│   ├── src/             # React components & pages
│   └── package.json
└── README.md
```

## API Endpoints

Main route groups:
- `/api/auth` - Authentication (register, login, verify)
- `/api/farmer` - Farmer operations
- `/api/hhm` - Hub Head Manager operations
- `/api/worker` - Worker operations
- `/api/factory` - Factory operations
- `/api/contracts` - Contract management
- `/api/listings` - Crop listings
- `/api/orders` - Order management
- `/api/analytics` - Analytics data

For detailed API documentation, check the route files in `backend/routes/`.

## Deployment

**Backend (Render):**
- Uses `backend/render.yaml`
- Health check: `/api/health`
- Environment: Node.js

**Frontend (Netlify):**
- Uses `frontend/netlify.toml`
- Build: `npm run build`
- Publish: `dist/`

## Troubleshooting

| Issue | Solution |
|-------|----------|
| MongoDB connection fails | Verify `MONGO_URI` and ensure MongoDB is running |
| CORS errors | Check `CORS_ORIGIN` in `.env` matches your frontend URL |
| Port already in use | Change `PORT` in `.env` |


