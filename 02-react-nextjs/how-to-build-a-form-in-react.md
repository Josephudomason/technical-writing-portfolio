---
title: "How to Build a Form in React"
description: "Build a beginner-friendly React form with controlled inputs, validation, submit handling, and loading state."
category: "React / Next.js"
audience: "Beginner developers"
difficulty: "Beginner"
---
# How to Build a Form in React

Forms look simple until you need validation, loading states, error messages, and API submission. A controlled form is a good beginner pattern because it keeps the input values in React state, where you can inspect and validate them before sending anything.

## Prerequisites

- Understanding of [props and state](props-vs-state-in-react.md)
- Basic HTML form elements
- A React project

## What Is a Controlled Form?

A controlled form stores each input value in React state and updates that state on every change. The input displays the state value, so React is the source of truth for the form.

## Why Controlled Forms Help

Controlled forms make validation and conditional UI easier. You can disable a submit button, show an error message, trim values, or decide whether the request should be sent at all.

## How It Works

Use `value` to bind the input to state and `onChange` to update the state. Use `onSubmit` on the form element so pressing Enter and clicking the submit button behave consistently.

## Example

This example validates a simple contact form before submitting. It is intentionally small, but the same pattern applies to signup forms, settings screens, and search forms.

```jsx
import { useState } from "react";

export default function ContactForm() {
  const [email, setEmail] = useState("");
  const [message, setMessage] = useState("");
  const [error, setError] = useState("");

  function handleSubmit(event) {
    event.preventDefault();

    if (!email.includes("@")) {
      setError("Enter a valid email address.");
      return;
    }

    setError("");
    console.log({ email, message });
  }

  return (
    <form onSubmit={handleSubmit}>
      <label>
        Email
        <input value={email} onChange={(event) => setEmail(event.target.value)} />
      </label>
      <label>
        Message
        <textarea value={message} onChange={(event) => setMessage(event.target.value)} />
      </label>
      {error ? <p role="alert">{error}</p> : null}
      <button type="submit">Send</button>
    </form>
  );
}
```

`event.preventDefault()` stops the browser from reloading the page. The validation checks the current state. The `role="alert"` helps assistive technology announce the error.

## Common Mistakes

- Using a button without `type="submit"` inside a form and getting unexpected behavior.
- Forgetting `event.preventDefault()` for client-side handling.
- Validating only on the client and skipping server-side validation.
- Showing vague errors such as `Invalid input`.

## Best Practices

- Use labels for every input.
- Keep validation messages specific.
- Disable submission while an async request is pending.
- Validate again on the server before trusting submitted data.

## Troubleshooting

If typing does not update the input, check that `value` and `onChange` use the same state variable. If the page reloads, confirm that `preventDefault()` runs inside `onSubmit`.

## What to Remember

Use controlled inputs when the UI needs to react to what the user typed. Keep the first version small: values, validation, submit handler, loading state, and a clear error message. Production forms should still validate on the server, even when the client-side validation feels complete.

## Next Steps

- Connect the form to an API after reading [Understanding APIs](../01-beginner-programming/understanding-apis-beginners-guide.md).
- If using Next.js, learn routing in [How Routing Works in Next.js](how-routing-works-in-nextjs.md).

## Further Reading

- [React input reference](https://react.dev/reference/react-dom/components/input)
- [React Responding to Events](https://react.dev/learn/responding-to-events)

