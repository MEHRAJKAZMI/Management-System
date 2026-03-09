<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

<p align="center">
<a href="https://github.com/laravel/framework/actions"><img src="https://github.com/laravel/framework/workflows/tests/badge.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

## TTMS (Teacher Training Management System)

Laravel 12 + AdminLTE based **Teacher Training Management System** with:

- **RBAC**: Spatie Roles/Permissions
- **Admin/Trainer/Teacher/Editor panels**
- **Programs / Classes / Sessions / Enrollments**
- **Attendance + Assessments + Marks + Results**
- **Certificates + DMC PDFs** (DomPDF) with **verification QR**
- **Reports** (PDF/CSV/Excel exports)
- **Documents** (versioning + download tracking + role-based access)
- **Audit logs**
- **System + Email notifications** (including scheduled session reminders)

### Requirements

- PHP 8.2+ (project targets PHP 8.2+)
- MySQL
- Node.js (for Vite assets)
- XAMPP users: ensure **`extension=gd`** is enabled for Excel/QR dependencies (`E:\xampp-8.2.12\php\php.ini`).

### Setup

```bash
composer install
npm install
php artisan migrate:fresh --seed
```

### Run (development)

```bash
composer run dev
```

App runs at `http://127.0.0.1:8000`.

### Demo users (seeded)

Password for all users: `password`

- Super Admin: `superadmin@example.com`
- Admin: `admin@example.com`
- Trainer: `trainer@example.com`
- Teacher: `teacher@example.com`
- Editor: `editor@example.com`

### Certificate verification

Public verification page:

- `/verify-certificate/{code}`

### Session reminders (scheduled)

A scheduled job is configured to run hourly:

- `php artisan ttms:send-session-reminders --hours=24`

With the default `.env` mail driver `log`, emails will be written to logs.
