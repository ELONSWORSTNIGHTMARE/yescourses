## Yescourses Prototype

Simple Flask-based prototype for the **yescourses** landing page, course area and admin panel.

### Features

- Modern black landing page with animated circles background
- Georgian copy, English brand name **yescourses**
- Header with navigation: `ფუნქციები`, `შემოგვიერთდი`
- Three pricing packs with “instead of” prices
- FAQ section in Georgian with slide-down answers
- Auth modal for registration/login (required before purchase)
- Simple purchase flow (no real bank yet) that:
  - stores users and purchases in SQLite
  - gates course pages so only logged-in + purchased users can access
- `/admin` page with hardcoded credentials:
  - username: `yestour`
  - password: `yestour111`
- Admin dashboard shows sold count per pack
- Admin can upload course videos (with order index) and delete them

### Running locally

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
python app.py
```

Open `http://127.0.0.1:5000` in your browser.

### Next steps for real payments

- Replace the fake `/buy/<pack_id>` logic with your Georgian bank payment integration.
- After successful callback from the bank, call the same DB insert that currently happens directly in `/buy/<pack_id>` so purchases and admin stats stay correct.

