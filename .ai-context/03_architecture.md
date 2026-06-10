# Architecture

## Tech Stack
- Frontend: React.js (Vite, Tailwind CSS v4, Zustand, React Router)
- Backend: FastAPI (Python, Passlib, python-jose)
- Database: MongoDB (Motor async driver)

## Directory Structure
- `/backend`: Python FastAPI app
  - `database.py`: AsyncIOMotorClient initialization and index configuration.
  - `/models`: Pydantic definitions for User, Asset, Booking, Audit, Notification.
  - `/utils/security.py`: JWT and bcrypt utilities.
  - `/dependencies/auth.py`: Token validation and RBAC.
  - `/routes/auth.py`: Login and Register endpoints.
- `/frontend`: React app
  - `/src/api/axiosClient.js`: Custom Axios instance with interceptors.
  - `/src/store/authStore.js`: Zustand store for user auth state.
  - `/src/components`: Reusable layout and routing wrappers (`ProtectedRoute.jsx`, `MainLayout.jsx`).
  - `/src/pages`: Screens (`Login.jsx`, `Register.jsx`, `Dashboard.jsx`).

## Environment Variables (Backend)
- `MONGODB_URL`
- `DATABASE_NAME`
- `SECRET_KEY`
- `ALGORITHM`
