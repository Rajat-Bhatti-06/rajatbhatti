# NoteKeeper

A simple notes app built with Flask, SQLite, and vanilla JavaScript.

---

## What it does

- Add, edit, delete notes
- Search notes by title
- Data is saved in a SQLite database

---



## How to Run

```bash
pip install flask
python app.py
```#

Open `http://127.0.0.1:5000` in your browser.

---

## App Flow

```
User fills form
      ↓
Click "Add Note"
      ↓
JS sends fetch() POST to Flask
      ↓
Flask saves to SQLite
      ↓
Notes reload from DB
      ↓
Note appears on screen
```

---

## API Endpoints

| Method | Route | What it does |
| GET | /notes | Get all notes |
| POST | /add | Add a note |
| PUT | /update/\<id\> | Edit a note |
| DELETE | /delete/\<id\> | Delete a note |

---

## Deploy on Vercel

1. Install Vercel CLI — `npm install -g vercel`
2. Add `vercel.json` to project root:

```json
{
  "version": 2,
  "builds": [{ "src": "app.py", "use": "@vercel/python" }],
  "routes": [{ "src": "/(.*)", "dest": "app.py" }]
}
```

3. Run `vercel` in the project folder and follow the prompts.

> Note: SQLite data won't persist on Vercel (serverless). For persistent storage use [Render.com](https://render.com) instead — it's free and works with SQLite.

---

## Tech Used

- Python + Flask
- SQLite
- HTML, CSS, JavaScript
