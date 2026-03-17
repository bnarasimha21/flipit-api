# FlipIt API

Backend API for the FlipIt card game application. Provides RESTful endpoints for managing player scores, leaderboards, game statistics, and recent game history.

## Features

- **Leaderboard by topic** -- Retrieve top 10 scores for any card game topic, ranked by a combined metric of time and clicks
- **Score submission** -- Players can submit their game results (name, time, clicks, topic)
- **Game statistics** -- Get total number of games played and distinct player count
- **Recent games** -- View the 20 most recently played games
- **Player directory** -- List all unique players

## Tech Stack

- **Runtime:** Node.js (ES Modules)
- **Framework:** Express.js 4.x
- **Database:** MongoDB (via Mongoose 5.x)
- **Middleware:** CORS, Morgan (logging), body-parser, method-override

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/api/getScores/:topic` | Get top 10 scores for a topic |
| `GET` | `/api/totalGames` | Get total number of games played |
| `GET` | `/api/recentGames` | Get 20 most recent games |
| `GET` | `/api/players` | Get list of all unique player names |
| `GET` | `/api/playersCount` | Get total number of unique players |
| `POST` | `/api/addScore` | Submit a new game score |

### Add Score Request Body

```json
{
  "name": "PlayerName",
  "totalseconds": 45,
  "clicks": 12,
  "topic": "animals",
  "createdDate": "2024-01-01T00:00:00Z"
}
```

## Setup / Installation

```bash
git clone https://github.com/bnarasimha21/flipit-api.git
cd flipit-api
npm install
```

Update the MongoDB connection string in `setup.js` with your own credentials, then:

```bash
npm start
```

The API will be running at `http://localhost:4000`.

## License

MIT
