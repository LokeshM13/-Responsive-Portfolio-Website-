# Responsive Portfolio Website

Professional portfolio website for **Lokesh M**, created for the Cognevance Technologies Full Stack Web Developer Project 1.

## Overview

This project is a responsive React portfolio with a Node.js/Express REST API. The contact form stores messages in SQLite and gives visitors clear feedback when a message is sent.

## Features

- Responsive desktop, tablet, and mobile layouts
- Animated hero entrance and scroll-reveal sections
- About, skills, project showcase, and contact sections
- Interactive project detail modal
- Mobile navigation and smooth scrolling
- Contact form validation and success/error states
- SQLite persistence through `POST /api/contact`
- Health check endpoint for deployment monitoring

## Technology stack

**Frontend:** React, Vite, CSS3, Lucide React  
**Backend:** Node.js, Express.js, SQLite  
**Deployment targets:** Vercel (frontend), Render (backend)

## Project structure

```text
frontend/       React + Vite application
backend/        Express API and SQLite setup
screenshots/    Submission screenshots (add after deployment)
docs/           Project report (add final PDF)
```

## Local setup

### Backend

```bash
cd backend
npm install
cp .env.example .env
npm run dev
```

The API runs at `http://localhost:5050` by default. SQLite creates `backend/portfolio.db` automatically on first start. Port `5050` avoids the macOS AirPlay Receiver service, which commonly occupies port `5000`.

### Frontend

```bash
cd frontend
npm install
npm run dev
```

Open `http://localhost:5173`. To use a deployed backend, create `frontend/.env` with:

```env
VITE_API_URL=https://your-render-service.onrender.com
```

## API documentation

### `POST /api/contact`

Accepts JSON with `name`, `email`, `subject`, and `message`. Returns `201` with the saved message ID. Invalid or incomplete data returns `400`.

### `GET /api/contact`

Returns all stored contact messages ordered newest first. This endpoint should be protected with authentication before using it for a private production dashboard.

### `GET /api/health`

Returns `{ "status": "ok" }`.

## Deployment

For Vercel, set the project root to `frontend` and configure `VITE_API_URL`. For Render, set the root directory to `backend`, build command `npm install`, start command `npm start`, and configure `FRONTEND_URL` to the deployed Vercel origin.

## Screenshots and report

Add final browser captures to `screenshots/` and the project report PDF to `docs/` before submission.

## Future enhancements

- Add admin authentication for viewing contact messages
- Add project filtering and a dedicated project detail route
- Add automated email notifications for new messages
- Add a CMS-backed blog and case studies

## Author

**Lokesh m**  
Full Stack Web Developer
Mysore Karnataka india 
