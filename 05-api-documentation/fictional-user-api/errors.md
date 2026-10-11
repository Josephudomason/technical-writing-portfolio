| Field | Details |
| --- | --- |
| Title | Errors |
| Description | Error response format, status codes, and validation examples for the fictional User API. |
| Category | API Documentation |
| Audience | Beginner developers |
| Difficulty | Beginner |

# Errors

The Fictional User API returns structured JSON errors. This page is part of a demonstration documentation project.

## Error Object

| Field | Type | Description |
| --- | --- | --- |
| `error.code` | string | Stable machine-readable error code |
| `error.message` | string | Human-readable summary |
| `error.details` | array | Optional validation details |
| `request_id` | string | Identifier useful when contacting support |

## Example Error

```json
{
  "error": {
    "code": "validation_failed",
    "message": "The request body contains invalid fields.",
    "details": [
      {
        "field": "email",
        "message": "Enter a valid email address."
      }
    ]
  },
  "request_id": "req_789"
}
```

## Common Status Codes

| Status | Code | Meaning |
| --- | --- | --- |
| `400` | `bad_request` | Malformed JSON or unsupported request shape |
| `401` | `unauthorized` | Missing, expired, or invalid token |
| `403` | `forbidden` | Authenticated client lacks permission |
| `404` | `not_found` | Requested resource does not exist |
| `409` | `conflict` | Request conflicts with an existing resource |
| `422` | `validation_failed` | Request body failed validation |
| `429` | `rate_limited` | Too many requests |
| `500` | `internal_error` | Unexpected server error |

## Validation Rules

Validation errors should identify the field and the corrective action when possible. Avoid vague messages such as <code>Invalid request</code> when a specific field caused the problem.

## Related Pages

- [API Overview](README.md)
- [Authentication](authentication.md)
- [Users endpoints](users.md)

