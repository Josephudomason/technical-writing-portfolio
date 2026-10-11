| Field | Details |
| --- | --- |
| Title | What Is OAuth? |
| Description | A simple explanation of OAuth 2.0, delegated access, scopes, and common use cases. |
| Category | Technical Concepts |
| Audience | Beginner developers |
| Difficulty | Beginner |

# What Is OAuth?

OAuth is a protocol for delegated access. It lets one application access limited resources on behalf of a user without receiving the user's password.

## Prerequisites

- Basic familiarity with web applications
- A willingness to connect concepts before memorizing tools

## What Is OAuth?

OAuth 2.0 uses roles such as resource owner, client, authorization server, and resource server. A client requests access, the user grants permission, and the client receives a token with limited scope.

## Why It Matters

OAuth is useful when users want to connect apps safely, such as allowing a calendar app to read calendar events without sharing the account password.

## Simple Diagram

```text
User approves access
  |
  v
Authorization server issues token
  |
  v
Client calls resource server
```

## Practical Example

A project management app might request permission to read a user's GitHub repositories so it can show linked pull requests.

## Common Misunderstandings

- Using OAuth as a password-sharing mechanism.
- Requesting broader scopes than needed.
- Confusing OAuth with OpenID Connect login.

## Summary

This concept appears in many developer workflows. Learn the mental model first, then connect it to real tools and code examples.

## Next Steps

- [Authentication vs Authorization](authentication-vs-authorization.md)
- [What Is JWT?](what-is-jwt.md)

## Further Reading

- [OAuth 2.0](https://oauth.net/2/)

