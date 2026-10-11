| Field | Details |
| --- | --- |
| Title | npm Beginner's Guide |
| Description | Understand npm, package.json, dependencies, scripts, and safe installation habits. |
| Category | Developer Tools |
| Audience | Beginner developers |
| Difficulty | Beginner |

# npm Beginner's Guide

npm is part package installer, part script runner, and part project metadata manager. This guide explains the files and commands beginners touch most often: `package.json`, the lockfile, dependencies, and scripts.

## Prerequisites

- Basic command-line familiarity
- A development project for practice
- Permission to install project dependencies or tools when the workflow requires it

## What Is npm?

npm is the default package manager distributed with Node.js. It installs packages, runs project scripts, and records dependency metadata in `package.json` and lockfiles.

## Why It Matters

npm matters because most JavaScript projects depend on shared packages and scripts. Understanding `package.json`, the lockfile, and install commands prevents many setup problems.

## Practical Workflow

1. Create `package.json` with `npm init` or use a framework CLI.
2. Install runtime dependencies with `npm install package-name`.
3. Install development-only tools with `npm install --save-dev package-name`.
4. Run scripts with `npm run script-name`.
5. Commit `package.json` and the lockfile so installations are reproducible.

## Example

```bash
npm init -y
npm install zod
npm install --save-dev eslint
npm run test
```

## Security and Data Handling

Review packages before installing them. Check package name spelling, maintenance history, and whether the package asks for unusual post-install behavior.

## Common Mistakes

- Deleting the lockfile to fix every dependency issue.
- Installing CLI tools globally when the project expects local versions.
- Confusing `dependencies` with `devDependencies`.
- Running unknown scripts without reading them.

## Best Practices

- Start with the official getting-started path.
- Make one change at a time when troubleshooting.
- Keep project configuration in source control when teammates need it.
- Document non-obvious setup steps in the project README.

## Troubleshooting

When something fails, copy the exact error message, identify which command or file produced it, and check whether the problem is local setup, configuration, permissions, or application code. Avoid deleting large folders or changing multiple settings before you understand the failure.

## Summary

When npm fails, avoid random fixes. Check the Node version, read the package error, preserve the lockfile when possible, and use the command the project expects.

## Next Steps

- Review related errors in [How to Fix npm Installation Errors](../06-troubleshooting/npm-installation-errors.md).
- Use source control practices from [Common Git Errors and How to Fix Them](../06-troubleshooting/common-git-errors.md).

## Further Reading

- [docs.npmjs.com/](https://docs.npmjs.com/)
- [docs.npmjs.com/about-package-json-and-package-lock-json-files/](https://docs.npmjs.com/about-package-json-and-package-lock-json-files/)

