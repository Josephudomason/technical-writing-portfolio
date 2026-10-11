| Field | Details |
| --- | --- |
| Title | Authentication vs Authorization |
| Description | Learn the difference between proving identity and granting access permissions. |
| Category | Technical Concepts |
| Audience | Beginner developers |
| Difficulty | Beginner |

# Authentication vs Authorization

Authentication and authorization are related, but they answer different questions.

## Prerequisites

- Basic familiarity with web applications
- A willingness to connect concepts before memorizing tools

## Authentication vs Authorization

Authentication asks, 'Who are you?' Authorization asks, 'What are you allowed to do?' A user can be authenticated and still not authorized to access a specific resource.

## Why It Matters

Clear separation prevents security bugs. Logging in should not automatically grant access to every account, admin page, or database record.

## Simple Diagram

```text
Login
  |
  v
Authentication: identity verified
  |
  v
Authorization: permissions checked
  |
  v
Resource access allowed or denied
```

## Practical Example

A support agent may authenticate successfully but only authorized managers can refund large transactions.

## Common Misunderstandings

- Checking only that a token exists.
- Putting authorization only in the frontend.
- Using roles without considering resource ownership.

## Summary

This concept appears in many developer workflows. Learn the mental model first, then connect it to real tools and code examples.

## Next Steps

- [What Is Authentication?](what-is-authentication.md)
- [What Is OAuth?](what-is-oauth.md)

## Further Reading

- [OWASP Authorization Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Authorization_Cheat_Sheet.html)

