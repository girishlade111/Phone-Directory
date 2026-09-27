# Phone Directory — Contact Directory Web App

A polished, single-page web app that displays a searchable **phone/contact directory** whose data lives in a Google Sheet — so the directory can be updated by editing the spreadsheet, with no code changes.

## What it does

- Loads contacts from a Google Sheet at runtime via the Google Sheets API (range `Sheet1!A1:I`)
- Renders them as cards with search/filter by name or role, "show more" pagination (6 at a time)
- Click a contact to open a detail modal: phone, WhatsApp, Instagram, X, Threads links, role, and an expandable address section
- Light/dark theme toggle (follows system preference), animated sparkle background
- No login, no backend, no build — everything is client-side in one file

## Tech stack

- Single-file HTML5 + CSS3 + vanilla JavaScript
- [Font Awesome 6](https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css) icons, [Inter](https://fonts.google.com/specimen/Inter) font
- [Google Sheets API v4](https://developers.google.com/sheets/api) as the data source

## Data & privacy note

- The repo itself contains **no contact names, phone numbers, or personal data** — all contact data lives in an external Google Sheet (spreadsheet ID configured at the top of `index.html`). Contact entries should be treated as sample/placeholder data, and no personal data of real people is stored or reproduced in this repository.
- `index.html` embeds a Google Sheets API key for read-only client-side access. It is restricted, but if you fork this repo, replace `API_KEY` and `SPREADSHEET_ID` with your own key/sheet.

## Quick start

1. Open `index.html` in a browser, or serve it:
   ```bash
   python3 -m http.server 8080   # then open http://localhost:8080
   ```
2. (Optional) Point it at your own sheet: edit `SPREADSHEET_ID`, `API_KEY`, and `RANGE` at the top of the `<script>` block in `index.html`. Your sheet must be readable via the Sheets API with that key.

Expected sheet columns (row 1 = headers): Name, Role, Phone, WhatsApp, Instagram, X, Threads, Address, etc.

## Project structure

```
.
├── index.html   # markup, styles, and app logic (Google Sheet loader, search, modal)
└── README.md
```

## Deployment

Fully static — deployed to **GitHub Pages**: https://girishlade111.github.io/Phone-Directory/

No environment variables or build step needed. The app needs internet access to reach Google Fonts/CDNs and the Sheets API.

---

Built by Girish Lade — https://ladestack.in
