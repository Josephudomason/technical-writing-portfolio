| Field | Details |
| --- | --- |
| Title | What Is REST? |
| Description | Understand REST APIs, resources, HTTP methods, status codes, and JSON responses. |
| Category | Technical Concepts |
| Audience | Beginner developers |
| Difficulty | Beginner |

# What Is REST?

REST is an architectural style often used for web APIs. REST APIs organize functionality around resources.

## Prerequisites

- Basic familiarity with web applications
- A willingness to connect concepts before memorizing tools

## What Is REST?

In a REST-style API, URLs represent resources, HTTP methods describe actions, and status codes describe outcomes. For example, `GET /users` lists users and `POST /users` creates a user.

## Why It Matters

REST conventions make APIs easier to learn because clients can predict how resources are named and manipulated.

## Simple Diagram

```text
GET /users      -> list users
POST /users     -> create user
GET /users/123  -> retrieve user
PATCH /users/123 -> update user
DELETE /users/123 -> delete user
```

## Practical Example

The fictional API in this portfolio uses REST-style user endpoints. See the [Fictional User API](../05-api-documentation/fictional-user-api/README.md).

## Common Misunderstandings

- Using verbs in every URL, such as `/getUsers`, instead of resource names.
- Returning `200 OK` for every outcome.
- Ignoring idempotency and method semantics.

## Summary

This concept appears in many developer workflows. Learn the mental model first, then connect it to real tools and code examples.

## Next Steps

- [What Is an API?](what-is-an-api.md)
- [What Is JSON?](what-is-json.md)

## Further Reading

- [Fielding REST dissertation chapter](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)
- [MDN HTTP request methods](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Methods)

