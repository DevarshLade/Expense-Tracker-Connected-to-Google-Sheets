# Expense Tracker — Connected to Google Sheets

A client-side expense-tracking web app that uses a Google Sheet as its database — no backend server, no sign-up, free to use. Add expenses, browse them by category and date, and have every record synced to a Google Sheet via the Sheets API v4.

## Features
- Add expenses with date, description, amount, and category
- Live expense list with category icons and color coding
- Category breakdown / summary view
- Data persistence in Google Sheets (read + append via Sheets API v4)
- Loading indicator and toast notifications
- Responsive layout, Font Awesome icons

## Tech Stack
- HTML5, CSS3, vanilla JavaScript (single `index.html`, no build step)
- Google Sheets API v4 (fetch-based REST calls)
- Font Awesome 6 (CDN) for icons

## Quick Start
```bash
git clone https://github.com/DevarshLade/Expense-Tracker-Connected-to-Google-Sheets.git
cd Expense-Tracker-Connected-to-Google-Sheets
# serve statically, e.g.
npx serve .
# then open the served URL in a browser
```
(Opening `index.html` directly via `file://` also works, though some browsers restrict `fetch` — a tiny static server is the safer option.)

## Configuration
At the top of the `<script>` block in `index.html`:
```js
const API_KEY   = '<YOUR_GOOGLE_API_KEY>';   // Google Cloud API key with Sheets API enabled
const SHEET_ID  = '<YOUR_SHEET_ID>';          // e.g. 1t5eVxXL8CTEINqSNGTlwe4vysr-UzZsSwj4UXtIGXD4
const SHEET_NAME = 'Sheet1';
```
Setup:
1. Create a Google Sheet with a header row (Date, Description, Category, Amount).
2. In Google Cloud Console, enable the Google Sheets API and create an API key.
3. Share the sheet so the key can access it (or make it readable appropriately).
4. Paste the key and sheet ID into the config constants above.

## Project Structure
```
Expense-Tracker-Connected-to-Google-Sheets/
├── index.html      # full app (markup, styles, scripts)
└── README.md
```

## Deploy Notes
Pure static site — deploy anywhere static files are served (GitHub Pages, Cloudflare Pages, Netlify). No build step and no server-side environment variables; the Sheets credentials are client-side config (use a restricted API key).

---
Built by Girish Lade — https://ladestack.in
