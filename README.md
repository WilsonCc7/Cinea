# 🎞️ Cinea

> A streaming platform with a film diary built in: watch, rate, review, and log films in one place, powered by a self-hosted Jellyfin server.

<!-- Badges: replace USER/REPO once the repo exists -->
![Status](https://img.shields.io/badge/status-in%20development-orange)
![License](https://img.shields.io/badge/license-MIT-blue)
![Jellyfin](https://img.shields.io/badge/powered%20by-Jellyfin-00a4dc)

<!-- Add a screenshot or GIF here -->
<!-- ![Cinea preview](docs/preview.png) -->

## About

Cinea is a web-based streaming service. The catalog is served by a **Jellyfin** media server that runs on the Cinea operator's own hardware, and Cinea wraps it in a clean viewing experience with the social features of a film-logging app.

Users don't need to set up anything. They create an account, browse the catalog, press play, then rate and review what they watched and keep a diary of it.

Jellyfin handles the media: storage, metadata, and transcoding. Cinea handles the experience: accounts, the player, and everything personal (ratings, reviews, diary, lists).

## Features

- ▶️ **Streaming:** watch films directly in the browser
- 👤 **User accounts:** sign up, log in, and keep your own profile
- 🔎 **Catalog browsing:** search and filter by title, genre, and year
- 📓 **Film diary:** log what you watched and when
- ⭐ **Ratings and reviews:** rate films and write short reviews
- 📌 **Watchlist:** save films you want to watch next
- 📋 **Custom lists:** curate collections like "Rainy day films"
- 📊 **Stats:** see your watching habits over time

> Some features are still in progress. See the [Roadmap](#roadmap) for current status.

## How it works

```
┌──────────┐      ┌───────────────────┐      ┌─────────────────────┐
│  Viewer  │ ───► │   Cinea Web App   │ ───► │   Jellyfin Server   │
│ (browser)│      │ accounts, player, │      │  (self-hosted media │
└──────────┘      │  diary, reviews   │      │  library + streams) │
                  └─────────┬─────────┘      └─────────────────────┘
                            │
                      ┌─────▼─────┐
                      │ Database  │  users, ratings,
                      └───────────┘  reviews, diary, lists
```

Viewers only talk to Cinea. Cinea's backend talks to Jellyfin on their behalf, so the Jellyfin server and its API key are never exposed to the public.

## Tech Stack

<!-- Replace with your actual stack -->

| Layer | Technology |
|-------|------------|
| Frontend | _e.g. React / Vue / Svelte_ |
| Backend | _e.g. Node.js / Laravel / Django_ |
| Database | _e.g. PostgreSQL / SQLite_ |
| Media server | [Jellyfin](https://jellyfin.org) (self-hosted) |

## Getting Started

### Prerequisites

- A machine or server to run **Jellyfin** (10.8 or newer recommended)
- A Jellyfin **API key** (Dashboard → API Keys)
- A library of media you have the rights to stream
- _Node.js / runtime version here_

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/USER/cinea.git
cd cinea

# 2. Install dependencies
npm install

# 3. Configure environment
cp .env.example .env

# 4. Run in development
npm run dev
```

### Configuration

Set these values in your `.env` file:

```env
JELLYFIN_URL=http://localhost:8096
JELLYFIN_API_KEY=your_api_key_here
DATABASE_URL=your_database_url_here
SESSION_SECRET=change_me
```

### Deployment notes

- Keep Jellyfin on a private network and let only the Cinea backend reach it.
- Serve Cinea over **HTTPS** through a reverse proxy (Nginx, Caddy, etc.).
- Streaming and transcoding are CPU-heavy, so plan bandwidth and hardware for your expected number of viewers.
- Back up your database regularly.

## Usage

1. Open Cinea in your browser and create an account.
2. Browse the catalog and press play on any film.
3. Rate it, write a review, and add it to your diary.

## Roadmap

- [ ] Jellyfin integration (catalog and metadata)
- [ ] User accounts and authentication
- [ ] Streaming player
- [ ] Ratings and reviews
- [ ] Diary
- [ ] Watchlist
- [ ] Custom lists
- [ ] Watching stats
- [ ] Follow other users and activity feed
- [ ] Admin dashboard for managing the catalog

## Content and Legal

Cinea is software only. Whoever runs a Cinea instance is responsible for the media on their server and must have the legal right to stream it, for example their own works, public domain films, or Creative Commons licensed content. Streaming copyrighted material without permission may violate copyright law.

Cinea is an independent project and is not affiliated with or endorsed by Jellyfin or Letterboxd.



## License

Distributed under the MIT License. See `LICENSE` for more information.

## Acknowledgments

- [Jellyfin](https://jellyfin.org): the free software media system this project builds on
- [Letterboxd](https://letterboxd.com): inspiration for the diary and social experience
