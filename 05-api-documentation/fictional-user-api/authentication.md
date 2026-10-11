| Field | Details |
| --- | --- |
| Title | Authentication |
| Description | Authentication requirements for the fictional User API, including bearer token usage and error responses. |
| Category | API Documentation |
| Audience | Beginner developers |
| Difficulty | Beginner |

# Authentication

The Fictional User API uses bearer token authentication for protected endpoints. This page is part of a demonstration API documentation project and does not describe a real production API.

## Authentication Header

Send the token in the <code>Authorization</code> header:

```http
Authorization: Bearer <token>
```

## Example Request

```http
GET /api/users HTTP/1.1
Host: api.example.com
Accept: application/json
Authorization: Bearer eyJhbGciOiJIUzI1NiIs...
```

## Token Requirements

- Tokens must be sent over HTTPS.
- Tokens must not be included in query strings.
- Clients should store tokens securely for their platform.
- Expired or invalid tokens return <code>401 Unauthorized</code>.
- Valid tokens without sufficient permissions return <code>403 Forbidden</code>.

## Public Endpoints

For this fictional API, <code>POST /api/users</code> can be configured as public when the product allows self-service registration. All list, retrieve, update, and delete operations require authentication.

## Security Notes

Bearer tokens grant access to whoever holds them. Do not log full tokens, paste them into public issues, or commit them to source control.

## Related Pages

- [API Overview](README.md)
- [Users endpoints](users.md)
- [Error responses](errors.md)

