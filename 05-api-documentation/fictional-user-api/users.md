---
title: "Users"
description: "Endpoint reference for creating, listing, retrieving, updating, and deleting users in a fictional REST API."
category: "API Documentation"
audience: "Beginner developers"
difficulty: "Beginner"
---
# Users

This page documents the user endpoints for the Fictional User API. The API is fictional and is provided only as a documentation demonstration.

## User Object

| Field | Type | Description |
| --- | --- | --- |
| `id` | string | Unique user identifier, such as `usr_123` |
| `name` | string | User's display name |
| `email` | string | Unique email address |
| `created_at` | string | ISO 8601 timestamp |
| `updated_at` | string | ISO 8601 timestamp |

## Create a User

Creates a user account.

| Property | Value |
| --- | --- |
| Method | `POST` |
| URL | `/api/users` |
| Authentication | Optional for public registration; required for admin-created users |

### Headers

| Header | Value |
| --- | --- |
| `Content-Type` | `application/json` |
| `Authorization` | `Bearer <token>` when required |

### Request Body

| Field | Type | Required | Validation |
| --- | --- | --- | --- |
| `name` | string | Yes | 1-80 characters |
| `email` | string | Yes | Valid email address; unique |
| `password` | string | Yes | At least 12 characters |

### Request Example

```http
POST /api/users HTTP/1.1
Host: api.example.com
Content-Type: application/json
Authorization: Bearer <token>
```

```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "example-password-123"
}
```

### Response Example

```json
{
  "id": "usr_123",
  "name": "John Doe",
  "email": "john@example.com",
  "created_at": "2026-10-06T09:30:00Z",
  "updated_at": "2026-10-06T09:30:00Z"
}
```

### Status Codes

| Status | Meaning |
| --- | --- |
| `201 Created` | User created |
| `400 Bad Request` | Invalid JSON |
| `409 Conflict` | Email already exists |
| `422 Unprocessable Entity` | Validation failed |

## List Users

Returns a paginated list of users.

| Property | Value |
| --- | --- |
| Method | `GET` |
| URL | `/api/users` |
| Authentication | Required |

### Query Parameters

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| `limit` | integer | No | Number of users to return. Default `20`, maximum `100`. |
| `cursor` | string | No | Pagination cursor from a previous response. |
| `email` | string | No | Filter by exact email address. |

### Request Example

```http
GET /api/users?limit=20 HTTP/1.1
Host: api.example.com
Accept: application/json
Authorization: Bearer <token>
```

### Response Example

```json
{
  "data": [
    {
      "id": "usr_123",
      "name": "John Doe",
      "email": "john@example.com",
      "created_at": "2026-10-06T09:30:00Z",
      "updated_at": "2026-10-06T09:30:00Z"
    }
  ],
  "pagination": {
    "next_cursor": null,
    "limit": 20
  }
}
```

## Get a User

Retrieves one user by ID.

| Property | Value |
| --- | --- |
| Method | `GET` |
| URL | `/api/users/:id` |
| Authentication | Required |

### Path Parameters

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| `id` | string | Yes | User ID such as `usr_123` |

### Response Example

```json
{
  "id": "usr_123",
  "name": "John Doe",
  "email": "john@example.com",
  "created_at": "2026-10-06T09:30:00Z",
  "updated_at": "2026-10-06T09:30:00Z"
}
```

### Status Codes

| Status | Meaning |
| --- | --- |
| `200 OK` | User found |
| `401 Unauthorized` | Missing or invalid token |
| `404 Not Found` | No user exists for the ID |

## Update a User

Updates one or more editable user fields.

| Property | Value |
| --- | --- |
| Method | `PATCH` |
| URL | `/api/users/:id` |
| Authentication | Required |

### Request Body

| Field | Type | Required | Validation |
| --- | --- | --- | --- |
| `name` | string | No | 1-80 characters |
| `email` | string | No | Valid email address; unique |

### Request Example

```http
PATCH /api/users/usr_123 HTTP/1.1
Host: api.example.com
Content-Type: application/json
Authorization: Bearer <token>
```

```json
{
  "name": "John A. Doe"
}
```

### Response Example

```json
{
  "id": "usr_123",
  "name": "John A. Doe",
  "email": "john@example.com",
  "created_at": "2026-10-06T09:30:00Z",
  "updated_at": "2026-10-06T10:15:00Z"
}
```

## Delete a User

Deletes a user by ID.

| Property | Value |
| --- | --- |
| Method | `DELETE` |
| URL | `/api/users/:id` |
| Authentication | Required |

### Request Example

```http
DELETE /api/users/usr_123 HTTP/1.1
Host: api.example.com
Authorization: Bearer <token>
```

### Response

A successful delete returns <code>204 No Content</code> with an empty response body.

## Error Responses

All endpoints may return the shared error format documented in [Errors](errors.md).

