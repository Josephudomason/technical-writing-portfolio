---
title: "Common Git Errors and How to Fix Them"
description: "Resolve common Git problems including merge conflicts, rejected pushes, detached HEAD, and untracked files."
category: "Troubleshooting"
audience: "Beginner developers"
difficulty: "Beginner"
---
# Common Git Errors and How to Fix Them

This troubleshooting guide explains how to diagnose the problem, identify likely causes, and apply fixes in a safe order.

## Symptoms

- Git refuses to push.
- A merge reports conflicts.
- Files appear as untracked.
- The terminal says you are in detached HEAD state.

## Common Causes

- The remote branch has commits you do not have locally.
- Two branches changed the same lines.
- You created files but did not stage them.
- You checked out a commit instead of a branch.

## Solution 1: Fix a rejected push

Fetch and integrate remote changes before pushing again. In shared repositories, avoid force-pushing unless the team expects it.

```bash
git fetch origin
git pull --rebase origin main
git push origin your-branch
```

## Solution 2: Resolve a merge conflict

Open each conflicted file, choose the correct final content, remove conflict markers, then stage and continue.

```bash
git status
git add path/to/file
git commit
```

## Solution 3: Recover from detached HEAD

If you made useful changes while detached, create a branch at the current commit before switching away.

```bash
git switch -c save-detached-work
```

## How to Prevent the Problem

- Run `git status` often.
- Pull or fetch before starting work.
- Make small commits.
- Use branches for features and fixes.
- Do not rewrite shared history without agreement.

## Summary

Start with the smallest possible fix, read the exact error message, and change one variable at a time. Most beginner troubleshooting problems become easier when you separate environment issues, dependency issues, and application code issues.

## Further Reading

- [Git and GitHub Beginner's Guide](../04-developer-tools/git-and-github-beginners-guide.md)
- [Git documentation](https://git-scm.com/docs)

