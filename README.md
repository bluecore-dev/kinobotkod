# KinoKod Bot

**Telegram bot that delivers films by code, with a web admin panel.** A viewer sends a code seen in a post or reel, the bot answers with the film from a private channel. Admins manage the catalogue, subscriptions and support from the panel.

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white) ![aiogram 3](https://img.shields.io/badge/aiogram%203-2CA5E0?logo=telegram&logoColor=white) ![Supabase](https://img.shields.io/badge/Supabase-3FCF8E?logo=supabase&logoColor=white) ![React 18](https://img.shields.io/badge/React%2018-61DAFB?logo=react&logoColor=white) ![Vite 6](https://img.shields.io/badge/Vite%206-646CFF?logo=vite&logoColor=white) ![Railway](https://img.shields.io/badge/Railway-0B0D0E?logo=railway&logoColor=white) ![Vercel](https://img.shields.io/badge/Vercel-000000?logo=vercel&logoColor=white)

**Live admin panel:** [kinobotkod.vercel.app](https://kinobotkod.vercel.app)

## Features

- **Film by code** — the bot looks the code up and forwards the film from the movie channel
- **Mandatory subscription** — access after joining the configured channels
- **Paid access** — card payment; admins approve or reject each payment from the bot
- **Support chat** — users write to the admins through the bot
- **Admin commands** — add films, broadcast, statistics
- **Multilingual** interface
- **Web admin panel** — users, films and support tickets on Supabase

## Architecture

```
kinobotkod/
├── main.py            # aiogram 3 entry point (long polling)
├── config.py          # settings from environment variables
├── handlers/          # start, movies, payment, support, admin, getid
├── middlewares/       # user registration / tracking
├── database/          # Supabase client and queries
├── services/          # business logic
├── languages.py       # UI texts
├── admin-panel/       # React + Vite admin panel (Vercel)
├── migrate*.sql       # database schema
├── Dockerfile         # container image
└── railway.toml       # Railway deployment
```

## Getting started

```bash
pip install -r requirements.txt
# create .env with the variables below
python main.py
```

| Variable | Purpose |
|---|---|
| `BOT_TOKEN`, `BOT_USERNAME` | Telegram bot from @BotFather |
| `SUPABASE_URL`, `SUPABASE_KEY` | Database |
| `ADMIN_IDS` | Comma-separated Telegram ids of admins |
| `CHANNELS`, `MOVIE_CHANNEL` | Mandatory channels and the film storage channel |
| `PAYMENT_CARD`, `PAYMENT_PRICE` | Paid access |

Admin panel: `cd admin-panel && npm install && npm run dev`.

> Secrets belong in environment variables of Railway / Vercel — never in the repository.

## Author

Built by **Bluecore Dev** — IT agency · Omonjon, full-stack developer (4+ years)

[+998 91 911 99 88](tel:+998919119988) · [socialmarketing.uz](https://socialmarketing.uz) · Telegram [@anvarov_911](https://t.me/anvarov_911) · [anvarov1170@gmail.com](mailto:anvarov1170@gmail.com)
