| Field | Details |
| --- | --- |
| Title | What Is JWT? |
| Description | Understand JSON Web Tokens, claims, signatures, and safe beginner usage. |
| Category | Technical Concepts |
| Audience | Beginner developers |
| Difficulty | Beginner |

# What Is JWT?

JWT stands for JSON Web Token. It is a compact token format often used to represent claims between systems.

## Prerequisites

- Basic familiarity with web applications
- A willingness to connect concepts before memorizing tools

## What Is JWT?

A JWT has three encoded parts: header, payload, and signature. The payload contains claims. The signature helps verify that the token was issued by a trusted party and was not changed.

## Why It Matters

JWTs are common in authentication and API authorization workflows, especially when services need to verify token claims without storing session data in one central place.

## Simple Diagram

```text
header.payload.signature
  |
  v
Server verifies signature
  |
  v
Claims are trusted if verification passes
```

## Practical Example

A token payload might contain a user ID, issuer, audience, and expiration time. Sensitive secrets should not be placed in the payload because JWT payloads are encoded, not automatically encrypted.

## Common Misunderstandings

- Putting passwords or secrets in token payloads.
- Trusting a JWT without verifying its signature.
- Ignoring expiration and audience claims.

## Summary

This concept appears in many developer workflows. Learn the mental model first, then connect it to real tools and code examples.

## Next Steps

- [What Is Authentication?](what-is-authentication.md)
- [What Is OAuth?](what-is-oauth.md)

## Further Reading

- [RFC 7519: JSON Web Token](https://datatracker.ietf.org/doc/html/rfc7519)

