---
title: "Async/Await Explained Simply"
description: "Learn how async and await work in JavaScript and how to use them for API requests."
category: "Beginner Programming"
audience: "Beginner developers"
difficulty: "Beginner"
---
# Async/Await Explained Simply

`async` and `await` make asynchronous JavaScript easier to read. They are commonly used when fetching data, reading files, waiting for timers, or performing work that finishes later.

## Prerequisites

- Basic JavaScript functions
- A beginner understanding of APIs from [Understanding APIs](understanding-apis-beginners-guide.md)
- Comfort reading simple error messages

## What Is Async/Await?

`async` marks a function as asynchronous. An async function always returns a Promise. `await` pauses inside that function until the Promise settles, then returns the resolved value or throws the rejected error.

## Why Async Code Matters

Without `async` and `await`, asynchronous code often requires chained `.then()` calls. Those chains are valid, but they can become difficult to follow when you need multiple steps, error handling, or conditional logic.

## How It Works

JavaScript starts the asynchronous operation and continues managing other work through the event loop. `await` does not block the entire browser. It only pauses the current async function until the awaited operation completes.

## Example

This example fetches a user from an API and handles failed requests.

```javascript
async function loadUser(userId) {
  const response = await fetch(`https://api.example.com/users/${userId}`);

  if (!response.ok) {
    throw new Error(`Request failed with status ${response.status}`);
  }

  const user = await response.json();
  return user;
}

loadUser("usr_123")
  .then((user) => console.log(user.name))
  .catch((error) => console.error(error.message));
```

`fetch()` returns a Promise for the HTTP response. `response.json()` also returns a Promise because parsing the response body can take time. The `if (!response.ok)` block turns non-success HTTP responses into clear JavaScript errors.

## Common Mistakes

- Using `await` outside an async function in environments that do not support top-level await.
- Forgetting to handle errors with `try...catch` or `.catch()`.
- Assuming `fetch()` throws for HTTP 404 or 500 responses. It only rejects for network-level failures.
- Running independent requests sequentially when `Promise.all()` would be better.

## Best Practices

- Use `try...catch` in UI code where you need to show a friendly error.
- Check `response.ok` before trusting API data.
- Use descriptive function names such as `loadUser` or `saveProfile`.
- Keep loading, success, and error states separate in UI code.

## Troubleshooting

If a value logs as `Promise { <pending> }`, you probably forgot to use `await` or `.then()`. If an API request appears stuck, check the Network tab in browser developer tools.

## What to Remember

Use `async` and `await` when code needs to wait for work that finishes later, such as a network request. The important habits are checking failed responses, handling errors, and keeping loading states clear in the UI.

## Next Steps

- Apply async code to API requests in [Understanding APIs](understanding-apis-beginners-guide.md).
- Learn UI loading states in [How to Build a Form in React](../02-react-nextjs/how-to-build-a-form-in-react.md).

## Further Reading

- [MDN async function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)
- [MDN Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)

