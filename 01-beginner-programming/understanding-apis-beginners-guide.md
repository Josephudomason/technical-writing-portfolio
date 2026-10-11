---
title: "Understanding APIs: A Beginner's Guide"
description: "A practical beginner guide to APIs, HTTP methods, requests, responses, and JSON."
category: "Beginner Programming"
audience: "Beginner developers"
difficulty: "Beginner"
---
# Understanding APIs: A Beginner's Guide

An API, or Application Programming Interface, is a defined way for software systems to communicate. Web developers commonly use APIs to send and receive data between a client application and a server.

## Prerequisites

- Basic JavaScript knowledge
- Optional: [Async/Await Explained Simply](async-await-explained.md)
- A tool such as Postman or a browser

## What Is an API?

An API describes what requests a client can make, what data the server expects, and what response the server returns. A REST API usually exposes URLs called endpoints, such as `/api/users`, and uses HTTP methods such as `GET`, `POST`, `PATCH`, and `DELETE`.

## Why APIs Matter

APIs let applications share capabilities without exposing their internal code. A weather app can request forecast data, an online store can create orders, and a dashboard can load user records through API endpoints.

## How It Works

A client sends an HTTP request with a method, URL, headers, and sometimes a body. The server processes the request and returns an HTTP response with a status code, headers, and usually a JSON body.

## Example

This example sends a `GET` request and reads JSON data.

```javascript
async function getUsers() {
  const response = await fetch("https://api.example.com/users");

  if (!response.ok) {
    throw new Error("Could not load users");
  }

  return response.json();
}
```

`GET` requests retrieve data. `response.ok` checks whether the status code is in the successful range. `response.json()` parses the response body into JavaScript values.

## Common Mistakes

- Sending secrets such as private API keys from browser code.
- Confusing authentication with authorization.
- Ignoring HTTP status codes.
- Assuming every API uses the same request body shape.

## Best Practices

- Read the API documentation before writing code.
- Validate user input before sending it to an API.
- Handle loading, empty, and error states.
- Use environment variables for configuration values that differ between development and production.

## Troubleshooting

If an API call fails, check the request URL, method, headers, body, and response status code. For browser CORS errors, remember that the server must allow the browser origin; client-side code cannot disable CORS safely.

## What to Remember

APIs are contracts between systems. Before writing code against an API, check the endpoint, method, headers, request body, response shape, and status codes. Most API bugs come from one of those details being slightly wrong.

## Next Steps

- Practice API testing with [Postman Beginner's Guide](../04-developer-tools/postman-beginners-guide.md).
- Read the fictional REST API example in [Fictional User API](../05-api-documentation/fictional-user-api/README.md).
- Review the concept article [What Is REST?](../08-technical-concepts/what-is-rest.md).

## Further Reading

- [MDN HTTP overview](https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Overview)
- [MDN Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)

