# Real-Time Location Dating App

A Django + Channels + Leaflet dating application for nearby discovery, private chat, and consent-based location sharing.

## Requirements

- Python 3.12+
- Redis (for Channels channel layer in production/dev)
- Django 5.x

## Local setup

1. Create and activate a virtual environment:

   ```bash
   cd dating_app
   python3 -m venv .venv
   source .venv/bin/activate
   ```

2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Copy environment variables:

   ```bash
   cp .env.example .env
   ```

   Keep `DEBUG=True` for local development. For production, set a long random
   `SECRET_KEY`, a PostgreSQL `DATABASE_URL`, `REDIS_URL`, HTTPS hosts, and the
   secure-cookie/HSTS settings shown in `.env.example`.

4. Apply migrations:

   ```bash
   python manage.py migrate
   ```

5. Create a superuser:

   ```bash
   python manage.py createsuperuser
   ```

6. Run the app:

   ```bash
   python manage.py runserver 0.0.0.0:8000
   ```

7. For Channels/Redis support in local development, run Redis if available:

   ```bash
   redis-server
   ```

## Default app URLs

- Login: /accounts/login/
- Signup: /accounts/signup/
- Map: /discovery/
- WebSocket chat: /ws/chat/<conversation_id>/
- WebSocket location updates: /ws/location/

## Production notes

- Use PostgreSQL and configure `DATABASE_URL`/`REDIS_URL` in production.
- Set `DEBUG=False`, `SECURE_SSL_REDIRECT=True`, and proper `ALLOWED_HOSTS`.
- Ensure HTTPS and secure cookies are enabled behind a reverse proxy.

## Testing

```bash
python manage.py test
```
# m1
# m1
