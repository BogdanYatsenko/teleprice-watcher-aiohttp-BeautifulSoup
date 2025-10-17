# TelePrice Watcher

A lightweight Telegram bot to track product prices and notify you on drops.

## Features
- Add product links to your watchlist
- Periodic price checks (async, aiohttp)
- Notifies when price decreases
- SQLite (local) or Postgres (production)
- One‑click deploy options (Docker / Fly.io)

## Quick Start (Local)
1. **Clone** the repo and enter the folder:
   ```bash
   git clone <your-repo-url>.git
   cd teleprice-watcher
   ```
2. **Create `.env`** from example and fill it:
   ```bash
   cp .env.example .env
   ```
3. **Install deps** and run dev bot:
   ```bash
   python -m venv .venv && . .venv/bin/activate
   pip install -r requirements.txt
   python dev_app.py
   ```

## Production (webhook)
Set `DATABASE_URL` to your Postgres URL and run:
```bash
pip install -r requirements.txt
python app.py
```

## Docker
```bash
docker build -t teleprice-watcher .
docker run --env-file .env -p 8080:8080 teleprice-watcher
```

## Environment Variables
- `TOKEN` — Telegram bot token
- `ADMIN` — Admin Telegram user id
- `DATABASE_URL` — `sqlite:///data.db` or Postgres URL

## 📝 License
Released under the **MIT License** © 2025 Bogdan Yatsenko.

📦 About the migration
This repository was migrated as part of my Portfolio Refresh. Originally developed locally; during migration I added README, .env.example, Docker/CI, and minor improvements.
