# AppDev

A full-stack starter with a React UI and a Node.js API.

The client runs on [http://localhost:5173](http://localhost:5173). The API runs on [http://localhost:3001](http://localhost:3001). During development, Vite proxies `/api` to the API.

## Tech stack

| Layer | Tools |
| --- | --- |
| Runtime | Node.js |
| API | Express, CORS, dotenv |
| UI | React |
| Bundler | Vite |
| Packages | npm workspaces |

## Requirements

- Node.js 20 or newer
- npm

On Windows PowerShell, if `npm` fails because running scripts is disabled, allow local scripts for your user and open a new terminal:

```powershell
Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
```

## Setup

From the project root:

```bash
npm install
npm run dev
```

Open [http://localhost:5173](http://localhost:5173). The page loads project details from `GET /api/overview` and shows the result of `GET /api/health`.

To change the API port, copy `server/.env.example` to `server/.env` and set `PORT`.

## Scripts

| Script | What it does |
| --- | --- |
| `npm run dev` | Starts the API and the React app together |
| `npm run dev:server` | API only, at `http://localhost:3001` |
| `npm run dev:client` | UI only, at `http://localhost:5173` |
| `npm run build` | Production build of the React app in `client/dist` |

## Project structure

```text
AppDev/
├── README.md
├── package.json          # workspace scripts
├── client/               # React UI (Vite)
│   ├── index.html
│   ├── vite.config.js
│   └── src/
│       ├── main.jsx
│       ├── App.jsx
│       └── index.css
└── server/               # Node.js API (Express)
    ├── .env.example
    └── src/
        └── index.js
```

## API

| Method | Path | Purpose |
| --- | --- | --- |
| `GET` | `/api/health` | Returns `{ ok, service, message }` |
| `GET` | `/api/overview` | Returns the app name, summary, and stack |
