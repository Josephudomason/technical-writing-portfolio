| Field | Details |
| --- | --- |
| Title | Getting Started With React Native |
| Description | Learn what React Native is, how it differs from web React, and how to start a mobile app. |
| Category | React Native / Mobile Development |
| Audience | Beginner developers |
| Difficulty | Beginner |

# Getting Started With React Native

React Native lets you build native mobile apps with React concepts. Instead of rendering HTML elements, React Native renders native platform components for iOS and Android.

## Prerequisites

- Basic React knowledge
- Node.js installed
- A mobile development setup or Expo for a faster beginner workflow

## What Is React Native?

React Native is a framework for building mobile applications using JavaScript or TypeScript and React. It provides components such as `View`, `Text`, `Image`, and `Pressable` instead of browser elements such as `div` and `button`.

## Where React Native Fits

React Native is useful when a team wants to share application logic and React knowledge across platforms while still producing native mobile apps. Expo can simplify setup, but Expo is not required to use React Native.

## How It Works

React describes the UI, and React Native connects that UI to native platform views. Styles use JavaScript objects and a subset of CSS-like properties. Development can happen through Expo tools or through a bare React Native setup.

## Example

A minimal React Native component looks like this.

```tsx
import { Text, View } from "react-native";

export default function App() {
  return (
    <View style={{ padding: 24 }}>
      <Text>Hello from React Native</Text>
    </View>
  );
}
```

`View` is a layout container, similar in purpose to a `div` but not the same element. `Text` is required for displaying text in React Native.

## Common Mistakes

- Using HTML elements such as `div` or `span` in React Native.
- Assuming all CSS properties work exactly the same as the web.
- Treating Expo as a requirement instead of a helpful toolchain option.
- Ignoring platform differences between iOS and Android.

## Best Practices

- Start with Expo if you want the fastest beginner setup.
- Use React Native components instead of web elements.
- Test on real devices when possible.
- Keep platform-specific code isolated and clearly named.

## Troubleshooting

If the app fails to start, check Node.js, package installation, and the development server logs. If UI does not appear, verify that text is inside a `Text` component.

## What to Remember

React Native lets you bring React patterns to mobile apps, but it is not the web in a smaller screen. Learn the native components, layout rules, navigation patterns, and device testing workflow early.

## Next Steps

- Compare web and mobile concepts in [React Native vs React](react-native-vs-react.md).
- Learn list rendering in [ScrollView vs FlatList](scrollview-vs-flatlist.md).
- For Expo-specific setup, see [Getting Started With Expo](../04-developer-tools/getting-started-with-expo.md).

## Further Reading

- [React Native documentation](https://reactnative.dev/docs/getting-started)
- [Expo documentation](https://docs.expo.dev/get-started/create-a-project/)

