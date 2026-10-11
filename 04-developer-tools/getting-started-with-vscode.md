| Field | Details |
| --- | --- |
| Title | Getting Started With VS Code |
| Description | Set up Visual Studio Code for beginner-friendly JavaScript and web development. |
| Category | Developer Tools |
| Audience | Beginner developers |
| Difficulty | Beginner |

# Getting Started With VS Code

VS Code is where many beginners spend most of their development time, so the goal is not to install every extension. Start with a clean workspace, a terminal, source control, and a few settings that make the project easier to work in.

## Prerequisites

- Basic command-line familiarity
- A development project for practice
- Permission to install project dependencies or tools when the workflow requires it

## What Is VS Code?

Visual Studio Code is a source code editor with an integrated terminal, file explorer, debugging tools, extensions, Git support, and language features.

## Why It Matters

VS Code matters because it is where editing, searching, running commands, debugging, and source control meet. A clean setup helps beginners notice project problems instead of fighting the editor.

## Practical Workflow

1. Open a project folder, not only a single file.
2. Use the Explorer to navigate files and the integrated terminal to run commands.
3. Install only extensions that match your stack.
4. Use Source Control view to inspect changes before committing.
5. Keep workspace settings in `.vscode/settings.json` only when the setting should be shared by the project.

## Example

```json
{
  "editor.formatOnSave": true,
  "files.eol": "\n",
  "typescript.tsdk": "node_modules/typescript/lib"
}
```

## Security and Data Handling

Be careful with extensions because they run with access to your editor environment. Install extensions from publishers you trust and review workspace recommendations.

## Common Mistakes

- Opening a file instead of the project folder.
- Installing many overlapping formatters.
- Ignoring the Problems panel.
- Committing local-only editor settings that should stay personal.

## Best Practices

- Start with the official getting-started path.
- Make one change at a time when troubleshooting.
- Keep project configuration in source control when teammates need it.
- Document non-obvious setup steps in the project README.

## Troubleshooting

When something fails, copy the exact error message, identify which command or file produced it, and check whether the problem is local setup, configuration, permissions, or application code. Avoid deleting large folders or changing multiple settings before you understand the failure.

## Summary

A good VS Code setup should make the project quieter, not busier. Keep extensions intentional, use the Problems panel, and document workspace settings only when teammates should share them.

## Next Steps

- Review related errors in [How to Fix npm Installation Errors](../06-troubleshooting/npm-installation-errors.md).
- Use source control practices from [Common Git Errors and How to Fix Them](../06-troubleshooting/common-git-errors.md).

## Further Reading

- [code.visualstudio.com/docs](https://code.visualstudio.com/docs)
- [code.visualstudio.com/docs/editing/getting-started/userinterface](https://code.visualstudio.com/docs/editing/getting-started/userinterface)

