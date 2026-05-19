# Learning Management System — Mohalla Tuition Center (MTC)

A full-stack platform for **The Quran Foundation’s Mohalla Tuition Program**, supporting tuition centers in underprivileged communities across Hyderabad. The public site showcases the program’s mission and impact; the admin and tutor portals manage centers, students, tutors, attendance, and reports.

**Live site:** [https://muhalla-tuition-center.netlify.app/](https://muhalla-tuition-center.netlify.app/)

---

## About

The Mohalla Tuition Program bridges the educational gap for children in slum areas through local tuition centers, mentorship, and community support. This project digitizes day-to-day operations: center management, student records, tutor workflows, daily attendance, Hadiya (stipend) tracking, and exportable reports (CSV/PDF).

The Quran Foundation is a registered non-profit based in Hyderabad, focused on educational, social, and cultural advancement for marginalized communities.

---

## Features

### Public website
- Hero, programs, impact stats, testimonials, and call-to-action sections
- Responsive UI with Tailwind CSS and Framer Motion animations
- YouTube embed for program media

### Admin dashboard (`/admin` → `/admin-dashboard`)
- JWT-secured login
- Overview analytics
- Tutor, student, and center management (including map/location tools)
- Attendance and report management
- Hadiya management
- Admin user management

### Tutor dashboard (`/tutor` → `/tutor-dashboard`)
- Tutor login and overview
- Student list and daily attendance marking

### Backend API
- Express.js REST API on port `5001`
- MongoDB with Mongoose models
- Role-based routes for `/admin` and `/tutor`
- File uploads, bcrypt passwords, JWT auth

---

## Tech stack

| Layer    | Technologies |
|----------|----------------|
| Frontend | React 19, Vite 6, React Router 7, Tailwind CSS, Ant Design, Axios, Leaflet/Google Maps |
| Backend  | Node.js, Express 4, Mongoose 8, JWT, bcrypt, Multer |
| Database | MongoDB |

---

## Project structure

```
├── backend/          # Express API (server.js, routes, controllers, models)
├── frontend/         # Vite + React SPA
└── README.md
```

---

## Getting started

### Prerequisites
- Node.js 18+
- MongoDB instance (local or Atlas)

### Backend

```bash
cd backend
npm install
```

Create `backend/.env`:

```env
DB_URL=your_mongodb_connection_string
SECRET_KEY=your_jwt_secret
```

```bash
npm start
```

API runs at `http://localhost:5001`.

### Frontend

```bash
cd frontend
npm install
```

Create `frontend/.env` (if required by your deployment):

```env
VITE_API_URL=http://localhost:5001
```

```bash
npm run dev
```

App runs at `http://localhost:5173` (default Vite port).

### Production build (frontend)

```bash
cd frontend
npm run build
```

Deploy the `frontend/dist` folder (e.g. Netlify).

---

## Routes (frontend)

| Path               | Description              |
|--------------------|--------------------------|
| `/`                | Public home page         |
| `/admin`           | Admin login              |
| `/admin-dashboard` | Admin portal (protected) |
| `/tutor`           | Tutor login              |
| `/tutor-dashboard` | Tutor portal             |

---

## License

ISC (backend package). See repository maintainers for usage terms.
