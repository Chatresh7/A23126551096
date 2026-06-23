# URL Shortener System

## Overview

This project is a URL Shortener application built using React and Material UI. It allows users to create shortened URLs, manage URL validity periods, track URL statistics, and monitor application events through an integrated logging middleware.

The application is designed with a modular architecture that separates UI components, business logic, API interactions, and logging functionality.

---

## Features

### URL Shortening

* Create shortened URLs from long URLs
* Support custom shortcodes
* Configure URL validity periods
* Process up to five URLs simultaneously

### URL Management

* View all generated URLs
* Search URLs by original URL or shortcode
* Sort URLs by:

  * Latest
  * Oldest
  * Most Clicks
  * Expiry Time

### Statistics

* Track total URLs created
* Display click counts
* Show creation timestamps
* Show expiration timestamps

### Persistence

* Local storage integration
* Data survives browser refreshes
* Automatic state restoration

### Logging Middleware

* Structured logging
* Event tracking
* Error monitoring
* API request logging

---

## Technology Stack

### Frontend

* React
* Vite
* Material UI
* JavaScript
* CSS

### Middleware

* TypeScript
* Fetch API

### Storage

* Browser Local Storage

---

## Project Structure

```text
project-root/
│
├── notification-app-fe/
│   │
│   ├── src/
│   │   ├── api/
│   │   ├── components/
│   │   ├── hooks/
│   │   ├── pages/
│   │   ├── utils/
│   │   ├── App.jsx
│   │   ├── App.css
│   │   └── main.jsx
│   │
│   ├── public/
│   ├── package.json
│   └── vite.config.js
│
├── logging-middleware/
│   ├── src/
│   ├── README.md
│   └── package.json
│
├── notification-system-design.md
└── README.md
```

---

## Installation

### Clone Repository

```bash
git clone <repository-url>
```

### Navigate to Frontend

```bash
cd notification-app-fe
```

### Install Dependencies

```bash
npm install
```

### Start Development Server

```bash
npm run dev
```

### Open Application

```text
http://localhost:5173
```

---

## Usage

### Create Short URLs

1. Enter a valid URL.
2. Specify validity duration.
3. Optionally enter a custom shortcode.
4. Click **Shorten URLs**.

### Search URLs

Use the search field to find URLs by:

* Original URL
* Shortcode

### Sort Records

Available options:

* Latest
* Oldest
* Most Clicks
* Expiry Time

### View Statistics

The statistics section displays:

* Total URLs
* Total Clicks
* Creation Times
* Expiration Times

---

## Data Model

```json
{
  "longUrl": "https://example.com",
  "shortcode": "abc123",
  "creationTime": "2026-01-01T10:00:00Z",
  "expiryTime": "2026-01-01T10:30:00Z",
  "clicks": 0
}
```

---

## Logging

The application generates structured logs for:

* URL creation
* Data loading
* Search operations
* Error handling
* User actions

Example:

```json
{
  "stack": "frontend",
  "level": "info",
  "package": "page",
  "message": "Short URL created"
}
```

---

## Design Principles

* Modular Architecture
* Separation of Concerns
* Reusable Components
* Maintainable Code Structure
* Extensible Design
* Client-Side Persistence

---

## Future Enhancements

* Backend database integration
* User authentication
* Real-time analytics
* Click history tracking
* QR code generation
* Advanced reporting dashboard
* Export functionality

---

## Security Considerations

* URL validation
* Shortcode uniqueness checks
* Error handling
* Input sanitization
* Secure token management

---

## License

This project is intended for educational and evaluation purposes.
