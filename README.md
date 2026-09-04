# Register Interface

A basic Flask register/login interface that stores credentials in a SQLite database. Passwords are hashed with bcrypt — never stored in plain text.

## Setup

```bash
cd register_app
python -m venv .venv
# Windows
.venv\Scripts\activate
# macOS / Linux
source .venv/bin/activate

pip install -r requirements.txt
python app.py
```

Then open http://127.0.0.1:5000 in your browser.

## Files

- `app.py` — Flask app, routes, bcrypt hashing, SQLite access
- `templates/` — Jinja2 templates (`base`, `index`, `register`, `login`, `dashboard`)
- `static/style.css` — minimal styling
- `users.db` — created automatically on first run

## Security notes

- Passwords are hashed with `bcrypt.gensalt()` and stored as a hash string.
- The Flask `secret_key` is hard-coded for development — change it before deploying.
- CSRF protection is not included; consider adding `Flask-WTF` before going to production.