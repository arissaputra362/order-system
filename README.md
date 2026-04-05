<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="320" alt="Laravel Logo"></a></p>

## Order System (Laravel)

This repository contains the Order System — a Laravel-based application scaffolded for development and testing. The project includes Docker support, PHPUnit configuration, frontend tooling via Vite, and example factories/migrations.

**Status:** Development

**Stack:** PHP (Laravel), MySQL/SQLite (configurable), Node (Vite), Docker (optional)

**Quick Links**
- **Repository:** [README.md](README.md)
- **Routes:** routes/web.php
- **Primary model:** app/Models/User.php

**Prerequisites**
- PHP 8.3+ and Composer
- Node.js 16+ and npm/yarn
- Docker & docker-compose (optional)

## Setup (Local)

1. Install PHP and Node dependencies:

```bash
composer install
npm ci
```

2. Copy the environment file and set your values:

```bash
cp .env.example .env
php artisan key:generate
```

3. Configure the database in `.env` (MySQL, PostgreSQL or SQLite). For a quick SQLite setup, set `DB_CONNECTION=sqlite` and create the file:

```bash
mkdir -p database && touch database/database.sqlite
```

4. Run migrations and seeders:

```bash
php artisan migrate --seed
```

5. Build frontend assets (dev):

```bash
npm run dev
```

6. Serve the app locally:

```bash
php artisan serve
```

## Docker (optional)

To run the application with Docker (uses `docker-compose.yml` in repo):

```bash
docker-compose up --build -d
```

After containers are up, run migrations inside the app container if needed:

```bash
docker-compose exec app php artisan migrate --seed
```

## Tests

Run the test suite with:

```bash
./vendor/bin/phpunit
```

Or using Artisan helper:

```bash
php artisan test
```

## Useful Commands

- Install dependencies: `composer install`, `npm ci`
- Generate app key: `php artisan key:generate`
- Migrate database: `php artisan migrate`
- Seed database: `php artisan db:seed`
- Run tests: `php artisan test` or `./vendor/bin/phpunit`
- Run queued jobs (sync by default): `php artisan queue:work`

## Project Structure (high level)

- `app/` — Models, Controllers, Providers
- `routes/` — Route definitions (web.php, console.php)
- `database/` — Migrations, factories and seeders
- `resources/` — Blade views and frontend assets
- `tests/` — Feature and unit tests

## Next Steps / Notes

- Update `.env` with real credentials before deploying.
- Consider setting up `supervisor` or a queue worker for background jobs in production.
- If you want, I can run the test suite or create a `.env.example` parity check.

---

If you want a commit and push for this README update, tell me and I will prepare the commit. If you'd like additional project-specific docs (API endpoints, ER diagram, or deployment steps), say which you'd prefer.
