# Traveler System (Flask + React Dashboard)

Production-style full-stack traveler management app with:
- Flask REST API (`127.0.0.1:5000`)
- React + Vite + Tailwind dashboard (`localhost:5173`)
- SQLite database with SQLAlchemy

## Folder Structure

```text
traveler system/
├─ app/
│  ├─ models/
│  │  ├─ traveler.py
│  │  └─ user.py
│  ├─ routes/
│  │  ├─ travelers.py
│  │  ├─ stats.py
│  │  └─ auth.py
│  ├─ services/
│  │  └─ traveler_service.py
│  ├─ utils/
│  │  ├─ validators.py
│  │  └─ errors.py
│  ├─ __init__.py
│  ├─ config.py
│  └─ extensions.py
├─ frontend/
│  ├─ src/
│  │  ├─ api/
│  │  ├─ components/
│  │  ├─ App.jsx
│  │  └─ index.css
│  ├─ package.json
│  └─ vite.config.js
├─ app.py
├─ run.py
├─ requirements.txt
└─ .env
```

## Backend Setup

1. Install dependencies:
   ```bash
   python -m pip install -r requirements.txt
   ```
2. Run backend:
   ```bash
   python app.py
   ```
3. API base URL:
   - `http://127.0.0.1:5000`

## Frontend Setup

1. Go to frontend:
   ```bash
   cd frontend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Run frontend:
   ```bash
   npm run dev
   ```
4. Open:
   - `http://localhost:5173`

## Environment Variables

Root `.env`:
```env
SECRET_KEY=change-this-secret
DATABASE_URL=sqlite:///travelers.db
```

Frontend `.env`:
```env
VITE_API_URL=http://127.0.0.1:5000
```

## REST API Endpoints

- `GET /travelers`
- `POST /travelers`
- `GET /travelers/<id>`
- `PUT /travelers/<id>`
- `DELETE /travelers/<id>`
- `GET /stats`
- `POST /auth/register`
- `POST /auth/login`

## Flask-Migrate Commands

```bash
flask --app run.py db init
flask --app run.py db migrate -m "initial migration"
flask --app run.py db upgrade
```
