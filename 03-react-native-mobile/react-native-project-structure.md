| Field | Details |
| --- | --- |
| Title | How to Structure a React Native Project |
| Description | A practical beginner guide to organizing screens, components, hooks, services, and assets in React Native. |
| Category | React Native / Mobile Development |
| Audience | Beginner developers |
| Difficulty | Beginner |

# How to Structure a React Native Project

A clear project structure helps a React Native app stay understandable as it grows. The goal is to group files by responsibility without creating folders that are too abstract for a beginner team.

## Prerequisites

- A React Native or Expo project
- Basic components and navigation
- Optional: [How Navigation Works in React Native](react-native-navigation.md)

## What Is Project Structure?

Project structure is the way source files are organized. A beginner-friendly React Native project usually separates screens, reusable components, API services, hooks, assets, and utilities.

## Why Structure Matters

Mobile apps often grow quickly: authentication, onboarding, settings, navigation, API calls, forms, and offline behavior. Good structure makes files easier to find and reduces accidental duplication.

## How It Works

Start simple. Put route-level screens in `src/screens`, reusable UI in `src/components`, API calls in `src/services`, hooks in `src/hooks`, and shared types in `src/types`. If using Expo Router, route files may live in `app`, while reusable code still lives under `src`.

## Example

This is a practical starting structure.

```text
src/
  components/
    Button.tsx
    EmptyState.tsx
  hooks/
    useSession.ts
  screens/
    HomeScreen.tsx
    SettingsScreen.tsx
  services/
    api.ts
  types/
    user.ts
assets/
  images/
app.json
```

The structure separates UI, screens, shared logic, and services. It remains small enough for beginners to understand without hiding code behind too many layers.

## Common Mistakes

- Creating many folders before the app needs them.
- Putting API calls directly in every screen.
- Duplicating similar components instead of extracting one reusable component.
- Mixing generated native files with app source code without understanding them.

## Best Practices

- Organize by responsibility at first, then by feature when the app becomes larger.
- Keep reusable components platform-aware.
- Use absolute imports only after configuring them correctly.
- Document any structure decision that differs from common conventions.

## Troubleshooting

If imports become hard to follow, review whether files are in the right layer. If circular dependencies appear, move shared types or utilities into a neutral folder.

## What to Remember

A useful project structure helps people find code without guessing. Start with a few obvious folders, keep shared logic out of screens, and reorganize by feature only when the app is large enough to benefit from it.

## Next Steps

- Add navigation with [How Navigation Works in React Native](react-native-navigation.md).
- Learn Expo workflow in [Getting Started With Expo](../04-developer-tools/getting-started-with-expo.md).

## Further Reading

- [React Native documentation](https://reactnative.dev/docs/getting-started)
- [Expo project structure guide](https://docs.expo.dev/get-started/start-developing/)

