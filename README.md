# Campus Legends

Daily quiz game: Guess which college 7 notable NFL & NBA players attended.

## Features

- New set of 7 players every day at **6:00 AM EST**
- Multiple choice (one shot only)
- Hints: short bio + famous teammate/coach
- Schools only revealed after all 7 answers
- Interactive map with clickable pins + facts
- Clean vertical share image for X / messages
- Special easter egg: **Ryan McAuliffe** (St. John's → Mets minors) appears every 4th day

## How to run / test

Because this is a pure static site (HTML + JS + CDN), you can:

1. Open `index.html` directly in a browser, **or**
2. Serve it locally:
   ```bash
   npx serve .
   ```
3. Deploy to Vercel / Netlify / GitHub Pages for a public link friends can use.

## Daily Logic

- Uses Eastern Time date as seed so everyone worldwide gets the same 7 players.
- Every 4th day of the year (`dayOfYear % 4 === 0`) forces Ryan McAuliffe into the lineup as the only baseball/minor-league player.

## Expanding the database

Edit `data/players.js`. Each player needs:
- id, name, sport, college, collegeShort
- city, state, lat, lng (for the map)
- years, hintBio, hintTeammate, facts
- difficulty (easy/medium/hard)
- isSpecial: true only for Ryan

Aim for 150–300 players for good variety.

## Tech

- Vanilla JS (no build step)
- Tailwind via CDN
- Leaflet for the map
- Canvas for the share image
- localStorage for today’s progress
