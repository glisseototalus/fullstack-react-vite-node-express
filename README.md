# Monorepo: Vite + React (client) & Node + Express (server)

## Structure
- `/client` — Vite + React frontend
- `/server` — Node.js + Express backend

## Setup

### 1. Install dependencies

```
cd client && npm install
cd ../server && npm install
```

### 2. Development

Run frontend and backend separately for development:

**Frontend (Vite + React):**
```
cd client
npm run dev
```

**Backend (Node + Express):**
```
cd server
npm run dev
```

- Frontend: [http://localhost:5173](http://localhost:5173)
- Backend/API: [http://localhost:3001](http://localhost:3001)

### 3. Production / Unified Deployment

To deploy as a single app (backend serves frontend):

1. **Build the frontend:**
	```
	cd client
	npm run build
	```
	This outputs static files to `client/dist`.

2. **Start the backend:**
	```
	cd server
	npm start
	```
	Express will serve the static frontend from `client/dist` and handle API routes.

**Now your users access both the frontend and API from the same server (default: http://localhost:3001).**

---

## Notes
- You can develop frontend and backend independently.
- For production, only the backend needs to be deployed (with the built frontend included).
- Adjust ports as needed in `server/index.js` or Vite config.
