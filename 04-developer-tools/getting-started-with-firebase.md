---
title: "Getting Started With Firebase"
description: "Set up Firebase in a JavaScript app and understand modular imports, services, and security rules."
category: "Developer Tools"
audience: "Beginner developers"
difficulty: "Beginner"
---
# Getting Started With Firebase

Firebase is a collection of hosted app services, not a single database or library. This guide starts with the web setup path and calls out the security rules beginners often miss.

## Prerequisites

- Basic command-line familiarity
- A development project for practice
- Permission to install project dependencies or tools when the workflow requires it

## What Is Firebase?

Firebase is Google's app development platform. Web developers commonly use Firebase Authentication, Cloud Firestore, Cloud Storage, Cloud Functions, and hosting-related services.

## Why It Matters

Firebase can save setup time, but it does not remove the need for access control. Beginners should treat security rules and service boundaries as part of the first implementation, not a later cleanup task.

## Practical Workflow

1. Create a Firebase project in the Firebase console.
2. Register a web app and copy the Firebase configuration.
3. Install the Firebase JavaScript SDK.
4. Initialize Firebase with `initializeApp`.
5. Import only the services your app uses.

## Example

```typescript
import { initializeApp } from "firebase/app";
import { getFirestore } from "firebase/firestore";

const firebaseConfig = {
  apiKey: process.env.NEXT_PUBLIC_FIREBASE_API_KEY,
  authDomain: process.env.NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN,
  projectId: process.env.NEXT_PUBLIC_FIREBASE_PROJECT_ID,
};

const app = initializeApp(firebaseConfig);
export const db = getFirestore(app);
```

## Security and Data Handling

Firebase web configuration identifies your project but does not replace security rules. Protect data with Firestore, Storage, and Authentication rules.

## Common Mistakes

- Using older namespaced SDK examples in a modular SDK project.
- Assuming Firebase config values are secret.
- Leaving database rules open during production.
- Importing entire services when a smaller modular import is enough.

## Best Practices

- Start with the official getting-started path.
- Make one change at a time when troubleshooting.
- Keep project configuration in source control when teammates need it.
- Document non-obvious setup steps in the project README.

## Troubleshooting

When something fails, copy the exact error message, identify which command or file produced it, and check whether the problem is local setup, configuration, permissions, or application code. Avoid deleting large folders or changing multiple settings before you understand the failure.

## Summary

A Firebase setup is not finished when the SDK initializes. The important follow-up work is deciding which services the app uses, locking down rules, and keeping client-side configuration separate from server-only secrets.

## Next Steps

- Review related errors in [How to Fix npm Installation Errors](../06-troubleshooting/npm-installation-errors.md).
- Use source control practices from [Common Git Errors and How to Fix Them](../06-troubleshooting/common-git-errors.md).

## Further Reading

- [firebase.google.com/docs](https://firebase.google.com/docs)
- [firebase.google.com/docs/web/setup](https://firebase.google.com/docs/web/setup)

