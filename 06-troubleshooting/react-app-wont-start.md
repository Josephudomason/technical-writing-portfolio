| Field | Details |
| --- | --- |
| Title | How to Fix a React App That Won't Start |
| Description | Diagnose and fix common reasons a React development server fails to start. |
| Category | Troubleshooting |
| Audience | Beginner developers |
| Difficulty | Beginner |

# How to Fix a React App That Won't Start

This troubleshooting guide explains how to diagnose the problem, identify likely causes, and apply fixes in a safe order.

## Symptoms

- The terminal exits after `npm run dev` or `npm start`.
- The browser shows a connection error.
- The terminal reports a missing script, missing package, or port conflict.

## Common Causes

- Dependencies were not installed.
- The wrong command is being used for the framework.
- Another process is already using the development port.
- Environment variables are missing.
- Node.js version does not match the project requirements.

## Solution 1: Install dependencies and use the project script

Run installation from the project root, then inspect `package.json` to find the correct script.

```bash
npm install
npm run dev
```

## Solution 2: Check the port

If the default port is already in use, stop the other process or choose another port supported by your tool.

```bash
npm run dev -- --port 3001
```

## Solution 3: Verify environment variables

Compare `.env.example` with your local `.env` file. Do not guess secret values; ask the project owner or create them in the relevant service dashboard.

## How to Prevent the Problem

- Commit an `.env.example` file without secrets.
- Document the correct start command in the README.
- Use a supported Node.js version manager.
- Avoid deleting lockfiles as a first troubleshooting step.

## Summary

Start with the smallest possible fix, read the exact error message, and change one variable at a time. Most beginner troubleshooting problems become easier when you separate environment issues, dependency issues, and application code issues.

## Further Reading

- [npm Beginner's Guide](../04-developer-tools/npm-beginners-guide.md)
- [React documentation](https://react.dev/learn)

