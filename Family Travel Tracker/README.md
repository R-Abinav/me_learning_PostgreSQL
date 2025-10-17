## Family Travel Tracker

Multi-user version of Travel Tracker. Each user has a name and color; visited countries are stored per user.

### Setup
1. Install deps: `npm install`
2. Create/seed DB `world` and tables:
   ```sql
   CREATE TABLE IF NOT EXISTS users (
     id SERIAL PRIMARY KEY,
     name TEXT NOT NULL,
     color TEXT NOT NULL
   );
   CREATE TABLE IF NOT EXISTS countries (
     country_code TEXT PRIMARY KEY,
     country_name TEXT NOT NULL
   );
   CREATE TABLE IF NOT EXISTS visited_countries (
     country_code TEXT REFERENCES countries(country_code),
     user_id INTEGER REFERENCES users(id),
     PRIMARY KEY (country_code, user_id)
   );
   ```
3. Adjust DB credentials in `index.js`.

### Run
```
node index.js
```
Open `http://localhost:3000`.

### Routes
- `GET /` → current user’s visited countries and color
- `POST /add` → add a visited country for current user
- `POST /user` → switch user or go to create user form
- `POST /new` → create a new user


