## World Flag Quiz

Guess the country name for a displayed flag image. Data is loaded from a PostgreSQL `flags` table.

### Setup
1. Install deps: `npm install`
2. Create DB `world` and a `flags` table seeded with `flags.csv`:
   ```sql
   CREATE TABLE IF NOT EXISTS flags (
     code TEXT PRIMARY KEY,
     name TEXT NOT NULL,
     image TEXT NOT NULL
   );
   ```
   Import CSV rows into `flags`.
3. Adjust DB credentials in `index.js`.

### Run
```
node index.js
```
Open `http://localhost:3000`.

### Flow
- On load, picks a random flag from in‑memory data (seeded from DB).
- Submit the country name; shows correctness and next flag with running score.


