# AI Class Room

An interactive fictional investigation platform built from `class.room`.

## Requirements

- Node.js 20+
- MongoDB (local or hosted)
- Google Gemini API key for case generation

## Start

1. Copy `.env.example` to `server/.env` and set `MONGODB_URI`, `JWT_SECRET`, and `GEMINI_API_KEY`.
2. Run `npm install` from the project root.
3. Run `npm run dev` and open http://localhost:5173.

The API listens on port 5000 by default. Case generation runs as a background task; the browser polls until it is ready. Cases are explicitly fictional. Image/video assets use clearly labeled evidence descriptions and CCTV simulation unless real media generation is configured.

## Structure

- `client/` React, Vite, Tailwind CSS application
- `server/` Express API, MongoDB models, auth, Gemini generation
- `class.room` source requirements

Passwords are bcrypt hashed. Authentication uses an HTTP-only cookie. The culprit and solution are stored in MongoDB but excluded from normal case responses; they are only returned after final answer submission.
