## World Capital Quiz

Quiz app that asks for capitals of random countries pulled from a PostgreSQL table.

### Setup
1. Install deps: `npm install`
2. Create DB `world` and a `capitals` table seeded with data from `capitals.csv`:
   ```sql
   CREATE TABLE IF NOT EXISTS capitals (
     country TEXT PRIMARY KEY,
     capital TEXT NOT NULL
   );
   ```
   Import CSV rows into `capitals`.
3. Adjust DB credentials in `index.js`.

### Run
```
node index.js
```
Open `http://localhost:3000`.

### Flow
- On load, fetch a random country from the in‑memory quiz array (seeded from DB at start).
- Submit an answer to check correctness and render the next question with updated score.


