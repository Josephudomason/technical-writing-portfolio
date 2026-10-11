| Field | Details |
| --- | --- |
| Title | Why Is My React Native ScrollView Not Scrolling? |
| Description | Fix React Native ScrollView problems caused by layout, flex styles, nested scrolling, and content size. |
| Category | Troubleshooting |
| Audience | Beginner developers |
| Difficulty | Beginner |

# Why Is My React Native ScrollView Not Scrolling?

This troubleshooting guide explains how to diagnose the problem, identify likely causes, and apply fixes in a safe order.

## Symptoms

- The content appears but does not move.
- Only part of the screen scrolls.
- Scrolling works on one platform but not another.
- Nested lists behave unpredictably.

## Common Causes

- The parent container has no bounded height.
- `contentContainerStyle` and `style` are being used for the wrong purpose.
- A nested scrollable component is capturing gestures.
- The content is not taller than the viewport.

## Solution 1: Give the parent a bounded height

A `ScrollView` needs a bounded height. In many screens, setting `flex: 1` on the screen container fixes the layout.

```tsx
import { ScrollView, View, Text } from "react-native";

export default function Screen() {
  return (
    <View style={{ flex: 1 }}>
      <ScrollView>
        <Text>Scrollable content</Text>
      </ScrollView>
    </View>
  );
}
```

## Solution 2: Use FlatList for long data lists

If you are rendering many repeated items, replace `ScrollView` with `FlatList` for better performance and more predictable list behavior.

## Solution 3: Separate container style from content style

`style` applies to the scroll view itself. `contentContainerStyle` applies to the inner content container.

## How to Prevent the Problem

- Use `FlatList` for long dynamic lists.
- Keep scrollable areas simple.
- Test on iOS and Android.
- Avoid nesting scroll views unless you understand the gesture behavior.

## Summary

Start with the smallest possible fix, read the exact error message, and change one variable at a time. Most beginner troubleshooting problems become easier when you separate environment issues, dependency issues, and application code issues.

## Further Reading

- [ScrollView vs FlatList](../03-react-native-mobile/scrollview-vs-flatlist.md)
- [React Native ScrollView docs](https://reactnative.dev/docs/scrollview)

