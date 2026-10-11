---
title: "What Is JSON?"
description: "Learn JSON syntax, data types, and why JSON is commonly used in APIs."
category: "Technical Concepts"
audience: "Beginner developers"
difficulty: "Beginner"
---
# What Is JSON?

JSON is a lightweight data format used to exchange structured data between systems.

## Prerequisites

- Basic familiarity with web applications
- A willingness to connect concepts before memorizing tools

## What Is JSON?

JSON stands for JavaScript Object Notation. It supports objects, arrays, strings, numbers, booleans, and `null`. Although inspired by JavaScript object syntax, JSON is a language-independent data format.

## Why It Matters

JSON is easy for humans to read and easy for programming languages to parse, which makes it common in web APIs and configuration files.

## Simple Diagram

```text
{
  "user": {
    "id": "usr_123",
    "name": "Maya"
  }
}
```

## Practical Example

An API response might return `{ "id": "usr_123", "email": "maya@example.com" }` so a frontend can display the user's profile.

## Common Misunderstandings

- Using single quotes in JSON.
- Leaving trailing commas.
- Putting comments in strict JSON.
- Confusing JSON text with a JavaScript object already parsed in memory.

## Summary

This concept appears in many developer workflows. Learn the mental model first, then connect it to real tools and code examples.

## Next Steps

- [What Is an API?](what-is-an-api.md)
- [Understanding APIs](../01-beginner-programming/understanding-apis-beginners-guide.md)

## Further Reading

- [MDN JSON](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Scripting/JSON)

