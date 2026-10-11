---
title: "Props vs State in React"
description: "Learn the difference between props and state in React and when to use each one."
category: "React / Next.js"
audience: "Beginner developers"
difficulty: "Beginner"
---
# Props vs State in React

Props and state are two core ways React components work with data. Props come from a parent component. State belongs to a component and can change over time.

## Prerequisites

- Basic understanding of [React components](how-react-components-work.md)
- Basic JavaScript objects
- A React project for practice

## What Are Props and State?

Props are read-only inputs passed into a component. State is data a component manages internally with hooks such as `useState`. Props answer, 'What did the parent give me?' State answers, 'What does this component need to remember?'

## Why the Difference Matters

Understanding props and state prevents many beginner React bugs. If you store everything in state, components become harder to reason about. If you expect props to change themselves, the UI will not update the way you expect.

## How It Works

A parent component passes props in JSX. A component creates state by calling `useState(initialValue)`, which returns the current value and a setter function. Calling the setter schedules a re-render with the new value.

## Example

This counter receives a label as a prop and stores the count as state.

```jsx
import { useState } from "react";

function Counter({ label }) {
  const [count, setCount] = useState(0);

  return (
    <button onClick={() => setCount(count + 1)}>
      {label}: {count}
    </button>
  );
}

export default function App() {
  return <Counter label="Likes" />;
}
```

`label` is a prop because the parent provides it. `count` is state because the `Counter` component updates it when the user clicks the button.

## Common Mistakes

- Trying to assign a new value directly to props.
- Duplicating props into state without a clear reason.
- Forgetting that state updates are scheduled, not applied as plain variable assignments.
- Using state for values that can be calculated during render.

## Best Practices

- Start with props for data from a parent.
- Use state only for values that change because of user input, network results, or time.
- Keep state as close as possible to the components that need it.
- Lift state up when multiple sibling components need the same value.

## Troubleshooting

If the UI does not update, confirm that you called the state setter instead of mutating the existing value. For arrays and objects, create a new array or object instead of changing the existing one in place.

## What to Remember

Use props for data a component receives. Use state for data a component needs to remember and change. When that rule feels unclear, ask which component should own the value.

## Next Steps

- Use state in forms with [How to Build a Form in React](how-to-build-a-form-in-react.md).
- Learn how state boundaries change in Next.js with [Server Components vs Client Components](server-components-vs-client-components.md).

## Further Reading

- [React State: A Component's Memory](https://react.dev/learn/state-a-components-memory)
- [React Passing Props to a Component](https://react.dev/learn/passing-props-to-a-component)

