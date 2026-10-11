| Field | Details |
| --- | --- |
| Title | React Native vs React: What's the Difference? |
| Description | Compare React for web and React Native for mobile with practical beginner examples. |
| Category | React Native / Mobile Development |
| Audience | Beginner developers |
| Difficulty | Beginner |

# React Native vs React: What's the Difference?

React and React Native share the same component model, but they target different platforms. React renders web interfaces. React Native renders mobile interfaces.

## Prerequisites

- Basic React knowledge
- Optional: [Getting Started With React Native](getting-started-with-react-native.md)

## What Do They Share?

Both use components, props, state, hooks, and JSX. A developer who understands React can transfer many mental models to React Native, especially component composition and state management.

## Why the Difference Matters

Knowing the difference prevents web assumptions from causing mobile bugs. The logic may feel familiar, but layout, styling, navigation, device APIs, and release workflows are different.

## How It Works

React uses DOM elements such as `div`, `input`, and `button`. React Native uses native components such as `View`, `TextInput`, and `Pressable`. Web navigation often uses URLs; mobile navigation usually uses stacks, tabs, and screens.

## Example

The same idea looks different across platforms.

```tsx
// React for web
function WebButton() {
  return <button>Save</button>;
}

// React Native for mobile
import { Pressable, Text } from "react-native";

function MobileButton() {
  return (
    <Pressable>
      <Text>Save</Text>
    </Pressable>
  );
}
```

The web version renders an HTML button. The React Native version uses native components and wraps visible text in `Text`.

## Common Mistakes

- Using CSS files the same way you would in a web app.
- Expecting browser APIs such as `localStorage` to exist by default.
- Assuming URL-based routing is the default navigation model.
- Skipping device testing because the app works in a simulator.

## Best Practices

- Reuse business logic where it makes sense, not platform-specific UI blindly.
- Learn React Native layout rules separately from web CSS.
- Use platform-aware libraries for storage, navigation, and device APIs.
- Test touch targets and keyboard behavior on real devices.

## Troubleshooting

If a web package fails in React Native, check whether it depends on browser APIs or Node.js APIs. Use packages that explicitly support React Native.

## What to Remember

The React mental model carries over to React Native, but the platform details change. Reuse concepts and business logic where they fit; treat UI, navigation, storage, and native APIs as mobile-specific concerns.

## Next Steps

- Learn navigation in [How Navigation Works in React Native](react-native-navigation.md).
- Review project organization in [How to Structure a React Native Project](react-native-project-structure.md).

## Further Reading

- [React documentation](https://react.dev/learn)
- [React Native documentation](https://reactnative.dev/docs/getting-started)

