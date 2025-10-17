## Travel Tracker

Track visited countries and visualize them on a map. Express + EJS frontend with PostgreSQL for storage.

### Setup
1. Install deps: `npm install`
2. Create DB `world` and tables:
   ```sql
   CREATE TABLE IF NOT EXISTS countries (
     country_code TEXT PRIMARY KEY,
     country_name TEXT NOT NULL
   );
   CREATE TABLE IF NOT EXISTS visited_countries (
     country_code TEXT PRIMARY KEY REFERENCES countries(country_code)
   );
   ```
   Seed `countries` with codes/names as needed.
3. Adjust DB credentials in `index.js` to match your local setup.

### Run
```
node index.js
```
Open `http://localhost:3000`.

### Routes
- `GET /` → render visited list and count
- `POST /add` → add by country name (fuzzy match to `countries` table)


