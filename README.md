# NEON DOMINION ONLINE

Node.js 18+ and WebSocket (`ws`) multiplayer game.

## Local run

```bash
npm install
npm start
```

Open http://localhost:3000 in your browser. Friends on the public internet need a deployed instance, not localhost.

## Deploy

1. Push the entire `neon-dominion` folder to a GitHub repository.
2. Create a **Web Service** on a hosting provider supporting persistent Node.js WebSocket connections (for example Render).
3. Build command: `npm install`; start command: `npm start`.
4. Share the provider's HTTPS URL. Clients automatically use WSS over HTTPS.
5. One server instance should host all rooms. In-memory rooms and IDs reset on server restart; no database or persistent accounts are included.

## Notes

- 10 total players per room; empty seats are filled with AI.
- `kk-001` style IDs are unique only within a running server process, **not globally persistent accounts**.
- `ROOM-0000` through `ROOM-9999` are generated and checked against active rooms.
- Rooms are temporary; the server is authoritative for movement, captures and skills.
- The game is a prototype, not a production-hardened service. Consider rate limiting, reconnection, database-backed accounts, authentication and multi-instance coordination for a public launch.
