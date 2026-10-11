---
title: "What Is a Cloud Database?"
description: "Understand cloud databases, managed services, backups, scaling, and beginner tradeoffs."
category: "Technical Concepts"
audience: "Beginner developers"
difficulty: "Beginner"
---
# What Is a Cloud Database?

A cloud database is a database hosted and managed through a cloud provider or backend platform.

## Prerequisites

- Basic familiarity with web applications
- A willingness to connect concepts before memorizing tools

## What Is a Cloud Database?

Cloud databases can be relational, document-based, key-value, or specialized systems. Managed providers often handle provisioning, backups, monitoring, updates, and scaling tools.

## Why It Matters

Cloud databases help teams avoid managing every server detail themselves. They are useful for prototypes, production apps, distributed teams, and systems that need managed backups or high availability.

## Simple Diagram

```text
Application
  |
  v
Internet or private network
  |
  v
Managed cloud database
```

## Practical Example

Supabase provides hosted PostgreSQL, while Firebase Cloud Firestore provides a managed NoSQL document database.

## Common Misunderstandings

- Assuming managed means security is automatic.
- Skipping backups and restore testing.
- Leaving databases publicly reachable without access controls.
- Choosing a database only because it is popular.

## Summary

This concept appears in many developer workflows. Learn the mental model first, then connect it to real tools and code examples.

## Next Steps

- [Getting Started With Supabase](../04-developer-tools/getting-started-with-supabase.md)
- [Getting Started With Firebase](../04-developer-tools/getting-started-with-firebase.md)

## Further Reading

- [Supabase docs](https://supabase.com/docs)
- [Firebase docs](https://firebase.google.com/docs)

