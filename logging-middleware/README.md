# Logging Middleware

## Overview

This project implements a reusable logging middleware for structured application logging. It enables frontend and backend applications to send standardized log entries to a centralized logging service.

## Features

* Structured logging format
* Frontend and backend support
* Multiple log severity levels
* Package-based categorization
* HTTP-based log transmission
* TypeScript implementation

## Supported Log Levels

* debug
* info
* warn
* error
* fatal

## Supported Stacks

* frontend
* backend

## Supported Packages

### Frontend

* api
* component
* hook
* page
* state
* style

### Shared

* auth
* config
* middleware
* utils

### Backend

* cache
* controller
* cron_job
* db
* domain
* handler
* repository
* route
* service

## Logger Function

```typescript
Log(
  stack,
  level,
  package,
  message
)
```

## Parameters

| Parameter | Description                          |
| --------- | ------------------------------------ |
| stack     | Application layer (frontend/backend) |
| level     | Severity level of the log            |
| package   | Source module generating the log     |
| message   | Log message description              |

## Example Usage

```typescript
await Log(
  "frontend",
  "info",
  "page",
  "Application initialized"
);
```

```typescript
await Log(
  "frontend",
  "error",
  "api",
  "Request failed"
);
```

## Log Structure

```json
{
  "stack": "frontend",
  "level": "info",
  "package": "page",
  "message": "Application initialized"
}
```

## Project Structure

```text
logging-middleware/
│
├── src/
│   └── logger.ts
│
└── README.md
```

## Technologies Used

* TypeScript
* Fetch API
* Vite
* ES6+

## Notes

* Logs are transmitted using HTTP requests.
* Authentication is handled through environment variables.
* The middleware validates log metadata before submission.
* Structured logs improve debugging, monitoring, and observability.
