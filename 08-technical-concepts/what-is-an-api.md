| Field | Details |
| --- | --- |
| Title | What Is an API? |
| Description | A simple explanation of APIs, requests, responses, endpoints, and why APIs matter. |
| Category | Technical Concepts |
| Audience | Beginner developers |
| Difficulty | Beginner |

# What Is an API?

An API is a defined way for software systems to communicate. Web APIs usually let a client request data or actions from a server.

## Prerequisites

- Basic familiarity with web applications
- A willingness to connect concepts before memorizing tools

## What Is an API?

API stands for Application Programming Interface. It is not the database itself and not necessarily the server itself. It is the contract that says what a client can ask for and what the server will return.

## Why It Matters

APIs make software reusable. A frontend can request users, a mobile app can submit transfers, and an internal dashboard can fetch reports without knowing every detail of the server code.

## Simple Diagram

```text
Client
  |
  v
API endpoint
  |
  v
Application server
  |
  v
Database
```

## Practical Example

A weather app might call `GET /forecast?city=Lagos` and receive JSON containing temperature, humidity, and forecast details.

## Common Misunderstandings

- Thinking an API is always public.
- Ignoring authentication requirements.
- Assuming all APIs are REST APIs.

## Summary

This concept appears in many developer workflows. Learn the mental model first, then connect it to real tools and code examples.

## Next Steps

- [Understanding APIs: A Beginner's Guide](../01-beginner-programming/understanding-apis-beginners-guide.md)
- [What Is REST?](what-is-rest.md)

## Further Reading

- [MDN HTTP overview](https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Overview)

