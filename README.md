# Prime Water Mobile App

A full-stack water utility management application with an Android frontend (Jetpack Compose + Kotlin) and a PHP REST API backend.

## Features

- **User Authentication** – Register, login, and OTP verification
- **Dashboard** – Real-time water consumption monitoring with animated gauge
- **Billing** – View bills with details, due dates, and payment status
- **Analytics** – Historical water usage trends and insights
- **Complaints** – File and track support tickets
- **Service Requests** – Submit new connection or modification requests
- **Payments** – In-app payment flow
- **Notifications & Announcements** – Push updates from the utility provider
- **Profile & Settings** – Manage account details and preferences

## Tech Stack

| Layer      | Technology                         |
| ---------- | ---------------------------------- |
| Frontend   | Kotlin, Jetpack Compose, Material 3 |
| Backend    | PHP (REST API)                     |
| Database   | MySQL                              |
| Networking | Retrofit + OkHttp                  |
| Auth       | Session-based with SharedPreferences |

## Screenshots

<!-- Add screenshots here: ![Dashboard](screenshots/dashboard.png) -->

## API Endpoints

| Endpoint               | Description            |
| ---------------------- | ---------------------- |
| `api_login.php`        | User login             |
| `api_register.php`     | User registration      |
| `api_dashboard.php`    | Dashboard data         |
| `api_mybill.php`       | Bill listing           |
| `api_bill_details.php` | Single bill details    |
| `api_mycomplaint.php`  | Complaint listing      |
| `api_submit_complaint.php` | File a complaint   |
| `api_myappList.php`    | Service requests       |
| `api_submit_request.php` | New service request  |
| `api_application.php`  | Application management |
| `api_analytics.php`    | Usage analytics        |

## Database Schema

The database (`primewater_db`) includes tables for `users`, `bills`, `complaints`, and `service_requests`. See [`Prime/schema.sql`](Prime/schema.sql) for the full schema.

## Setup

### Backend

1. Import `Prime/schema.sql` into your MySQL database.
2. Update database credentials in `Prime/db_config.php`.
3. Deploy the `Prime/` folder to a PHP-enabled web server.

### Android App

1. Open `AndroidApp/` in Android Studio.
2. Update the API base URL in `util/Config.kt` to point to your server.
3. Build and run.

```bash
./gradlew assembleDebug
```

## Project Structure

```
NewPrimeMobileapp/
├── AndroidApp/          # Android application (Kotlin + Jetpack Compose)
│   └── app/src/main/java/com/primewater/primewatermobile/
│       ├── api/         # Retrofit API service & client
│       ├── model/       # Data models
│       ├── ui/          # Screens, components, navigation, theme, viewmodels
│       └── util/        # Session manager, config
├── Prime/               # PHP REST API backend
│   ├── api_*.php        # API endpoints
│   ├── db_config.php    # Database configuration
│   └── schema.sql       # Database schema
├── .gitignore
└── README.md
```
