---
title: "Fictional User API Documentation"
description: "Overview documentation for a fictional REST API used to demonstrate professional API documentation."
category: "API Documentation"
audience: "Beginner developers"
difficulty: "Beginner"
---
# Fictional User API Documentation

This documentation describes the Fictional User API, a demonstration REST API created for documentation portfolio purposes. It is not connected to a real service, bank, employer, or production system.

## Base URL

```text
https://api.example.com
```

## Resources

The API manages user records with the following endpoints:

| Method | Endpoint | Purpose |
| --- | --- | --- |
| POST | `/api/users` | Create a user |
| GET | `/api/users` | List users |
| GET | `/api/users/:id` | Retrieve one user |
| PATCH | `/api/users/:id` | Update one user |
| DELETE | `/api/users/:id` | Delete one user |

## Authentication

Most endpoints require a bearer token. See [Authentication](authentication.md) for header format, token handling, and security notes.

## Common Headers

| Header | Required | Description |
| --- | --- | --- |
| `Authorization` | Yes, except where noted | `Bearer <token>` |
| `Content-Type` | For JSON request bodies | `application/json` |
| `Accept` | Recommended | `application/json` |

## Response Format

Successful responses return JSON. Error responses use the shared error object documented in [Errors](errors.md).

## Endpoint Reference

Read [Users](users.md) for endpoint-specific request bodies, query parameters, responses, validation rules, and status codes.

