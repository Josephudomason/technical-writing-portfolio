| Field | Details |
| --- | --- |
| Title | How React Components Work |
| Description | Understand React components, JSX, composition, and rendering with beginner-friendly examples. |
| Category | React / Next.js |
| Audience | Beginner developers |
| Difficulty | Beginner |

# How React Components Work

React components are reusable pieces of UI. A component can render a button, a form, a navigation bar, a page section, or an entire screen.

## Prerequisites

- Basic HTML
- Basic JavaScript functions
- Comfort with JavaScript objects from [JavaScript Objects Explained](../01-beginner-programming/javascript-objects-explained.md)

## What Is a React Component?

A React component is usually a JavaScript function that returns JSX. JSX looks like HTML, but it is JavaScript syntax that React uses to describe UI. Components can receive inputs called props and can be combined to build larger interfaces.

## Why Components Matter

Components help developers split a UI into small, understandable parts. Instead of editing one large file for an entire page, you can build and test smaller pieces with clear responsibilities.

## How It Works

React calls your component function and uses the returned JSX to decide what should appear on the screen. When data changes, React re-renders the relevant components and updates the browser efficiently.

## Example

This component renders a profile card from props.

```jsx
function ProfileCard({ name, role }) {
  return (
    <article>
      <h2>{name}</h2>
      <p>{role}</p>
    </article>
  );
}

export default function TeamPage() {
  return (
    <main>
      <ProfileCard name="Ada Lovelace" role="Frontend Engineer" />
      <ProfileCard name="Grace Hopper" role="Systems Engineer" />
    </main>
  );
}
```

`ProfileCard` is reusable because it receives `name` and `role` as props. `TeamPage` renders the same component twice with different values.

## Common Mistakes

- Starting component names with lowercase letters.
- Returning multiple sibling elements without a parent element or fragment.
- Putting unrelated responsibilities in one large component.
- Mutating props directly.

## Best Practices

- Name components with PascalCase.
- Keep components focused on one clear UI responsibility.
- Extract repeated UI into reusable components.
- Use props for data that comes from a parent component.

## Troubleshooting

If a component does not render, check that it is exported, imported, and used with a capitalized name. If JSX fails to compile, check for unclosed tags or invalid JavaScript inside braces.

## What to Remember

A good component has a clear job, a readable name, and inputs that make sense. If a component becomes hard to explain in one sentence, it may be doing too much.

## Next Steps

- Learn the difference between inputs and memory in [Props vs State in React](props-vs-state-in-react.md).
- Build a controlled input in [How to Build a Form in React](how-to-build-a-form-in-react.md).

## Further Reading

- [React Learn](https://react.dev/learn)
- [React Components and Props](https://react.dev/learn/your-first-component)

