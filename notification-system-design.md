# Notification System Design

## Overview

The Notification System is responsible for managing shortened URLs, tracking metadata, storing URL information, and displaying statistics to users. The system is designed as a client-side application with local persistence and modular architecture.

## Objectives

* Create shortened URLs from long URLs.
* Support custom shortcodes.
* Allow configurable validity periods.
* Store URL information persistently.
* Provide URL statistics and analytics.
* Support searching and sorting of URL records.
* Integrate logging middleware for application events.

---

## Architecture

```text
User Interface
      |
      v
Notifications Page
      |
      v
Custom Hook (State Management)
      |
      v
API Layer
      |
      v
Local Storage
```

### Components

#### Notifications Page

Responsible for:

* URL creation interface
* Statistics display
* URL listing
* User interactions

#### Notification Filter

Provides:

* Search functionality
* Sorting functionality

#### Custom Hook

Handles:

* Data loading
* State management
* Filtering
* Sorting
* URL creation
* Logging integration

#### API Layer

Responsible for:

* Reading stored URL data
* Creating new shortened URLs
* Updating statistics
* Managing local persistence

#### Logging Middleware

Captures:

* Page events
* User actions
* Errors
* System messages

---

## URL Data Model

```json
{
  "longUrl": "https://example.com",
  "shortcode": "abc123",
  "creationTime": "2026-01-01T10:00:00Z",
  "expiryTime": "2026-01-01T10:30:00Z",
  "clicks": 0
}
```

### Field Description

| Field        | Description                   |
| ------------ | ----------------------------- |
| longUrl      | Original URL                  |
| shortcode    | Generated or custom shortcode |
| creationTime | Creation timestamp            |
| expiryTime   | Expiration timestamp          |
| clicks       | Number of URL visits          |

---

## URL Creation Flow

```text
User enters URL
        |
        v
Validate Input
        |
        v
Generate Shortcode
(Optional Custom Code)
        |
        v
Calculate Expiry Time
        |
        v
Store URL Record
        |
        v
Update Statistics
        |
        v
Create Log Entry
```

---

## Search Flow

```text
User enters search term
        |
        v
Filter URL Collection
        |
        v
Display Matching Results
```

---

## Sorting Flow

Supported sorting options:

* Latest
* Oldest
* Most Clicks
* Expiry Time

```text
User selects sort option
        |
        v
Sort URL Collection
        |
        v
Render Updated Table
```

---

## Statistics Module

The statistics section provides:

* Total URLs created
* Total click count
* Creation timestamps
* Expiry timestamps

Future enhancements may include:

* Daily analytics
* Most visited URLs
* Expired URL tracking
* Click trends

---

## Data Persistence

The application uses browser local storage.

### Benefits

* Fast access
* No backend dependency
* Simple implementation
* Persistent across browser refreshes

### Storage Flow

```text
Create URL
      |
      v
Store in Local Storage
      |
      v
Reload Application
      |
      v
Restore Stored Data
```

---

## Logging Design

Logs are generated for:

* URL creation
* Data loading
* User actions
* Errors
* System events

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

## Scalability Considerations

Potential future improvements:

* Backend database integration
* Authentication and user accounts
* Real-time analytics
* Distributed logging
* URL click tracking service
* Role-based access control

---

## Security Considerations

* Input validation
* URL format verification
* Shortcode uniqueness validation
* Expiry enforcement
* Error handling
* Secure token management

---

## Conclusion

The notification system provides a modular architecture for URL shortening, statistics tracking, local persistence, and application monitoring. The design emphasizes simplicity, maintainability, and extensibility while supporting the core functional requirements.
