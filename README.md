## MediBridge

Full‑stack healthcare appointment platform with separate patient app, doctor portal, and admin portal.

### Features
- Patient booking: browse doctors by speciality, book/reschedule/cancel, view history
- Role‑based auth: users, doctors, admins via JWT and middleware guards
- Doctor portal: profile, availability, appointments dashboard
- Admin portal: add/verify doctors, manage appointments, earnings overview
- Media uploads: Multer + Cloudinary for profile/doc images
- Responsive UI built with React + TailwindCSS

### Monorepo Structure
- `frontend/` – Patient web app (Vite + React)
- `admin/` – Admin/Doctor web app (Vite + React)
- `backend/` – Node.js/Express API with MongoDB/Mongoose

### Tech Stack
React, Vite, TailwindCSS, Context API, Node.js, Express.js, MongoDB/Mongoose, JWT, Multer, Cloudinary.

---

## Prerequisites
- Node.js 18+
- MongoDB (Atlas or local)
- Cloudinary account (for image storage)

## Environment Variables

Create the following files before running locally.

Backend: `backend/.env`
```
PORT=4000
MONGODB_URI=mongodb+srv://<user>:<pass>@<cluster>/<db>?retryWrites=true&w=majority
JWT_SECRET=replace_with_strong_secret
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
CLIENT_URL=http://localhost:5173
ADMIN_URL=http://localhost:5174
```

Frontend (patient app): `frontend/.env`
```
VITE_BACKEND_URL=http://localhost:4000
```

Admin/Doctor app: `admin/.env`
```
VITE_BACKEND_URL=http://localhost:4000
```

Optional (patient app link to admin from navbar):
```
VITE_ADMIN_URL=http://localhost:5174
```

> Note: The patient navbar falls back to `https://your-admin-url.vercel.app` if `VITE_ADMIN_URL` is not set.

---

## Local Development

Install dependencies (run once per package):
```bash
cd backend && npm i
cd ../frontend && npm i
cd ../admin && npm i
```

Run all apps (in three terminals):
```bash
# API
cd backend && npm run dev

# Patient app
cd frontend && npm run dev

# Admin/Doctor app
cd admin && npm run dev
```

Common scripts:
```bash
npm run dev     # dev server (frontend/admin) or nodemon (backend)
npm run build   # production build (frontend/admin)
```

---

## Deployment Notes
- Frontends: deploy on Vercel/Netlify. Set `VITE_BACKEND_URL` and `VITE_ADMIN_URL` envs.
- Backend: deploy on Render/railway/fly. Set MongoDB, JWT, Cloudinary, and CORS origins (`CLIENT_URL`, `ADMIN_URL`).

---

## Project Links
- Patient app: <your live URL>
- Admin/Doctor app: <your live URL>
- API base: <your API URL>

---

## License
This project is for educational/portfolio use. Add a license if you intend broader distribution.


