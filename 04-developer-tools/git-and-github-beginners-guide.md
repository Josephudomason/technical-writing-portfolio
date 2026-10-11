---
title: "Git and GitHub Beginner's Guide"
description: "Learn Git version control, GitHub repositories, commits, branches, and pull requests."
category: "Developer Tools"
audience: "Beginner developers"
difficulty: "Beginner"
---
# Git and GitHub Beginner's Guide

Git helps you keep a history of your work. GitHub helps you share that history with other people. This guide keeps the focus on the workflow a junior developer is most likely to use on a team: branch, commit, push, and open a pull request.

## Prerequisites

- Basic command-line familiarity
- A development project for practice
- Permission to install project dependencies or tools when the workflow requires it

## What Is Git and GitHub?

Git is a version control system that records changes in a project. GitHub is a platform that hosts Git repositories and adds collaboration features such as pull requests, issues, reviews, and Actions.

## Why It Matters

Git and GitHub help teams review changes, recover earlier work, and collaborate without passing project folders around. The workflow matters more than memorizing every command.

## Practical Workflow

1. Create a local repository with `git init` or clone an existing repository.
2. Make small, focused changes.
3. Stage files with `git add`.
4. Commit the staged snapshot with `git commit`.
5. Push your branch to GitHub and open a pull request for review.

## Example

```bash
git clone https://github.com/example/project.git
cd project
git checkout -b add-readme-notes
git status
git add README.md
git commit -m "Add README notes"
git push origin add-readme-notes
```

## Security and Data Handling

Do not commit passwords, tokens, `.env` files, or private keys. Add local secret files to `.gitignore` and rotate any secret that was accidentally pushed.

## Common Mistakes

- Committing unrelated changes together.
- Working directly on `main` in a shared project.
- Ignoring `git status` before committing.
- Force-pushing shared branches without coordination.

## Best Practices

- Start with the official getting-started path.
- Make one change at a time when troubleshooting.
- Keep project configuration in source control when teammates need it.
- Document non-obvious setup steps in the project README.

## Troubleshooting

When something fails, copy the exact error message, identify which command or file produced it, and check whether the problem is local setup, configuration, permissions, or application code. Avoid deleting large folders or changing multiple settings before you understand the failure.

## Summary

The best beginner Git habit is small, reviewable changes. Check `git status` often, commit related work together, and avoid rewriting shared history unless your team explicitly agrees.

## Next Steps

- Review related errors in [How to Fix npm Installation Errors](../06-troubleshooting/npm-installation-errors.md).
- Use source control practices from [Common Git Errors and How to Fix Them](../06-troubleshooting/common-git-errors.md).

## Further Reading

- [git-scm.com/docs](https://git-scm.com/docs)
- [docs.github.com/en/get-started](https://docs.github.com/en/get-started)

