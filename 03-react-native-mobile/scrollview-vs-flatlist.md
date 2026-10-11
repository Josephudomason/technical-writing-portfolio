---
title: "Understanding ScrollView vs FlatList"
description: "Learn when to use ScrollView and FlatList in React Native and how to avoid performance issues."
category: "React Native / Mobile Development"
audience: "Beginner developers"
difficulty: "Beginner"
---
# Understanding ScrollView vs FlatList

`ScrollView` and `FlatList` both display scrollable content in React Native, but they are designed for different jobs. Choosing the wrong one can cause slow rendering and memory problems.

## Prerequisites

- Basic React Native components
- Understanding of arrays and rendering lists
- Optional: [Getting Started With React Native](getting-started-with-react-native.md)

## What Are ScrollView and FlatList?

`ScrollView` renders all of its children at once. `FlatList` renders list data efficiently and can render only the items needed around the visible area. Use `ScrollView` for small, fixed content and `FlatList` for long or dynamic lists.

## Why the Choice Matters

Mobile devices have limited memory and CPU compared with desktop development machines. Rendering hundreds of views at once can make an app feel slow or unstable.

## How It Works

`ScrollView` wraps children directly. `FlatList` receives a `data` array and a `renderItem` function. `FlatList` also supports item keys, separators, pull-to-refresh, headers, footers, and pagination patterns.

## Example

Use `FlatList` for a list of messages.

```tsx
import { FlatList, Text } from "react-native";

const messages = [
  { id: "msg_1", text: "Welcome" },
  { id: "msg_2", text: "Your order shipped" },
];

export default function MessagesScreen() {
  return (
    <FlatList
      data={messages}
      keyExtractor={(item) => item.id}
      renderItem={({ item }) => <Text>{item.text}</Text>}
    />
  );
}
```

`data` provides the list. `keyExtractor` gives each item a stable key. `renderItem` describes how one item should appear.

## Common Mistakes

- Using `ScrollView` for long API-driven lists.
- Using array indexes as keys when stable IDs exist.
- Nesting scrollable lists in ways that break gestures.
- Doing expensive work inside `renderItem`.

## Best Practices

- Use `FlatList` for data-driven lists.
- Use `ScrollView` for small settings screens or static content.
- Provide stable item keys.
- Memoize expensive item components when needed.

## Troubleshooting

If a `ScrollView` is not scrolling, check parent container height and flex styles. If `FlatList` feels slow, inspect item rendering cost and avoid inline heavy calculations.

## What to Remember

Use `ScrollView` for small, mostly static content. Use `FlatList` for data-driven lists that can grow. That one choice prevents many performance and layout problems in beginner React Native apps.

## Next Steps

- Read [Why Is My React Native ScrollView Not Scrolling?](../06-troubleshooting/react-native-scrollview-not-scrolling.md) for layout fixes.
- Learn structure in [How to Structure a React Native Project](react-native-project-structure.md).

## Further Reading

- [React Native ScrollView](https://reactnative.dev/docs/scrollview)
- [React Native FlatList](https://reactnative.dev/docs/flatlist)

