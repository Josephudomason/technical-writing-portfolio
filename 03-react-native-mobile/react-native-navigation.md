---
title: "How Navigation Works in React Native"
description: "Understand screen navigation, stacks, tabs, and beginner setup patterns in React Native."
category: "React Native / Mobile Development"
audience: "Beginner developers"
difficulty: "Beginner"
---
# How Navigation Works in React Native

Mobile apps usually navigate between screens instead of web pages. React Native does not include a full navigation system by itself, so many projects use libraries such as React Navigation or Expo Router.

## Prerequisites

- Basic React Native components
- A React Native or Expo project
- Optional: [React Native vs React](react-native-vs-react.md)

## What Is Mobile Navigation?

Mobile navigation controls how users move between screens. Common patterns include stack navigation for forward/back flows, tab navigation for major app sections, and modal screens for focused tasks.

## Why Navigation Matters

Navigation shapes the user's mental model of the app. Poor navigation makes screens hard to find, back behavior unpredictable, and state difficult to manage.

## How It Works

A navigator owns a set of screens. Each screen receives navigation helpers and route information. In a stack navigator, opening a screen pushes it onto the stack; going back pops it off.

## Example

This simplified React Navigation example creates a home screen and details screen.

```tsx
import { NavigationContainer } from "@react-navigation/native";
import { createNativeStackNavigator } from "@react-navigation/native-stack";
import { Button, Text, View } from "react-native";

const Stack = createNativeStackNavigator();

function HomeScreen({ navigation }) {
  return (
    <View>
      <Text>Home</Text>
      <Button title="Open details" onPress={() => navigation.navigate("Details")} />
    </View>
  );
}

function DetailsScreen() {
  return <Text>Details</Text>;
}

export default function App() {
  return (
    <NavigationContainer>
      <Stack.Navigator>
        <Stack.Screen name="Home" component={HomeScreen} />
        <Stack.Screen name="Details" component={DetailsScreen} />
      </Stack.Navigator>
    </NavigationContainer>
  );
}
```

`NavigationContainer` manages navigation state. The stack declares available screens. `navigation.navigate("Details")` opens the Details screen.

## Common Mistakes

- Installing only one navigation package and missing required peer dependencies.
- Using screen names inconsistently.
- Passing large objects through navigation params instead of IDs.
- Ignoring back behavior on Android.

## Best Practices

- Choose one navigation approach early.
- Use typed route params in TypeScript projects.
- Pass IDs through navigation and load detailed data inside the destination screen.
- Keep top-level navigation structure small and predictable.

## Troubleshooting

If navigation fails at runtime, verify installation instructions for your exact library and platform. Missing native dependencies are a common cause in bare React Native projects.

## What to Remember

Navigation is part of the app architecture, not just a way to move between screens. Keep screen names consistent, pass small route params, and test back behavior on the platforms you support.

## Next Steps

- Compare list components in [ScrollView vs FlatList](scrollview-vs-flatlist.md).
- Organize screens with [How to Structure a React Native Project](react-native-project-structure.md).

## Further Reading

- [React Navigation documentation](https://reactnavigation.org/docs/getting-started/)
- [Expo Router documentation](https://docs.expo.dev/router/introduction/)

