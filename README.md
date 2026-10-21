# H-OSINT — Open-Source Intelligence Platform

A full-stack web application that correlates identifiers (name, ID, email, phone, username, address, company) across **social media, public records, financial registries, and authorized threat-intelligence feeds** — with lawful-use safeguards built in.

## The problem
Investigators, security researchers, and due-diligence teams pull from a dozen disconnected sources by hand. H-OSINT unifies authorized, open, and public sources behind one search, shows only meaningful results, and requires a lawful-use acknowledgment before anything runs.

## Features
- **Multi-identifier search** — name, national ID, passport, email, phone, username, address, company
- **Social media** — cross-platform username-presence checks (GitHub, X, LinkedIn, Instagram, Reddit, …)
- **Public property** — land-registry portals, address geocoding via OpenStreetMap
- **Financial records** — SEC EDGAR, OpenCorporates, corporate-registry links
- **Open / deep web** — DuckDuckGo + SearX, Internet Archive, exposure indexes, paste-dump search
- **Dark web** — Ahmia `.onion` index and breach correlation via **authorized threat-intelligence feeds** (not direct Tor/marketplace access)
- **Results-only display** — empty sources and negative matches are hidden
- **Required legal acknowledgment** before any search runs
- **Modular source plugins** — add a source by extending `BaseSource` and registering it

## Tech
**Backend:** Python 3.11+ · FastAPI · Pydantic · httpx (async)
**Frontend:** React 18 · TypeScript · Vite · Tailwind CSS · lucide-react

## Quick start
```bash
# Backend
cd backend && python -m venv .venv && . .venv/bin/activate
pip install -r requirements.txt
uvicorn app.main:app --reload --port 8000

# Frontend
cd frontend && npm install && npm run dev   # http://localhost:5173
```

## API
`GET /api/health` · `GET /api/sources` · `POST /api/search` · `GET /api/history` · `GET /api/history/{id}`

## Architecture
```
H-OSINT/
├── backend/   # FastAPI routes, Pydantic models, source orchestrator & modules
└── frontend/  # React + TypeScript single-page console
```

## Legal & ethical use
Intended for **authorized** investigations, security research, due diligence, and journalism, in compliance with applicable privacy law (GDPR, CCPA, etc.) and platform terms. The dark-web module uses authorized threat-intelligence feeds only.

## Role
Sole architect and developer — API design, source-orchestration engine, and React/TypeScript front-end.

---
*For authorized, lawful use only.*
