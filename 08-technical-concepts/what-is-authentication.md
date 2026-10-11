---
title: "What Is Authentication?"
description: "A beginner-friendly explanation of authentication and how applications verify identity."
category: "Technical Concepts"
audience: "Beginner developers"
difficulty: "Beginner"
---
# What Is Authentication?

Authentication is the process of verifying who a user or system is.

## Prerequisites

- Basic familiarity with web applications
- A willingness to connect concepts before memorizing tools

## What Is Authentication?

When you log in with an email and password, use a one-time code, or authenticate with a passkey, the application is checking identity. Authentication is different from authorization, which decides what the verified identity can do.

## Why It Matters

Without authentication, an application cannot reliably connect actions and data to the right user.

## Simple Diagram

```text
User enters credentials
  |
  v
Server verifies identity
  |
  v
Session or token is issued
```

## Practical Example

A banking app asks for a password and second factor before showing account information.

## Common Misunderstandings

- Confusing authentication with authorization.
- Storing passwords directly instead of password hashes.
- Relying only on client-side checks.

## Summary

This concept appears in many developer workflows. Learn the mental model first, then connect it to real tools and code examples.

## Next Steps

- [Authentication vs Authorization](authentication-vs-authorization.md)
- [What Is JWT?](what-is-jwt.md)

## Further Reading

- [OWASP Authentication Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html)

