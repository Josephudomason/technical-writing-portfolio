| Field | Details |
| --- | --- |
| Title | How to Fix CORS Errors in a Web Application |
| Description | Understand and fix browser CORS errors by configuring the server instead of weakening the client. |
| Category | Troubleshooting |
| Audience | Beginner developers |
| Difficulty | Beginner |

# How to Fix CORS Errors in a Web Application

This troubleshooting guide explains how to diagnose the problem, identify likely causes, and apply fixes in a safe order.

## Symptoms

- The browser console mentions CORS policy.
- The request works in Postman but fails in the browser.
- Preflight `OPTIONS` requests fail.
- The response is blocked even though the server returned data.

## Common Causes

- The server does not allow the browser origin.
- Required headers or methods are missing from CORS configuration.
- Credentials are used without the correct CORS settings.
- The API is meant for server-to-server use, not direct browser access.

## Solution 1: Configure CORS on the server

The server must decide which origins, methods, and headers are allowed. The browser enforces that decision.

```javascript
app.use(cors({
  origin: "http://localhost:3000",
  methods: ["GET", "POST", "PATCH", "DELETE"],
  allowedHeaders: ["Content-Type", "Authorization"]
}));
```

## Solution 2: Use a backend proxy for private APIs

If an API requires a private key or does not allow browser requests, call it from your backend and expose only the safe operation to the frontend.

## Solution 3: Check credentials configuration

When sending cookies or HTTP credentials, the server cannot use wildcard origin `*`. It must return the specific allowed origin and allow credentials.

## How to Prevent the Problem

- Design browser-facing APIs with CORS in mind.
- Keep private API keys on the server.
- Test requests from the actual frontend origin.
- Document allowed origins for each environment.

## Summary

Start with the smallest possible fix, read the exact error message, and change one variable at a time. Most beginner troubleshooting problems become easier when you separate environment issues, dependency issues, and application code issues.

## Further Reading

- [MDN CORS guide](https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/CORS)
- [Understanding APIs](../01-beginner-programming/understanding-apis-beginners-guide.md)

