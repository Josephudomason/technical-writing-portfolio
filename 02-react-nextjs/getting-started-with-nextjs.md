| Field | Details |
| --- | --- |
| Title | Getting Started With Next.js |
| Description | Create a modern Next.js app using the App Router, TypeScript, and common project conventions. |
| Category | React / Next.js |
| Audience | Beginner developers |
| Difficulty | Beginner |

# Getting Started With Next.js

Next.js is a React framework for building web applications. It adds file-based routing, server rendering, data fetching patterns, optimization features, and deployment-friendly conventions.

## Prerequisites

- Node.js installed
- Basic React knowledge
- Comfort using a terminal

## What Is Next.js?

Next.js builds on React by providing application structure. The current App Router uses the `app` directory, layouts, pages, Server Components, Client Components, and file conventions for routing and metadata.

## Where Next.js Fits

React handles UI composition, but a production web app also needs routing, performance, loading states, server rendering, image optimization, and deployment workflows. Next.js provides these pieces as framework conventions.

## How It Works

Create a project with `create-next-app`. Pages are built from folders inside `app`. A `page.tsx` file defines a route's UI, and a `layout.tsx` file wraps route segments with shared UI.

## Example

Create a new project and add a basic route.

```bash
npx create-next-app@latest my-next-app
cd my-next-app
npm run dev
```

The CLI asks setup questions such as TypeScript and ESLint. After the dev server starts, create `app/about/page.tsx` to add an `/about` route.

## Common Mistakes

- Mixing Pages Router and App Router examples without understanding the difference.
- Adding `use client` to every component by default.
- Putting secrets in client-side code.
- Fetching data in the browser when it can safely be fetched on the server.

## Best Practices

- Use the App Router for new applications unless your team has a Pages Router reason.
- Keep interactive components small and mark only those files with `use client`.
- Use environment variables for configuration.
- Read framework release notes before upgrading major versions.

## Troubleshooting

If a route returns 404, confirm that the folder contains `page.tsx` or `page.jsx`. If a component using `useState` fails in the App Router, add `use client` at the top of that component file.

## What to Remember

Use Next.js when a React app needs framework-level decisions for routing, rendering, data loading, and deployment. For new projects, learn the App Router first and reach for Client Components only when the UI needs browser behavior.

## Next Steps

- Understand rendering boundaries in [Server Components vs Client Components](server-components-vs-client-components.md).
- Learn file-based routing in [How Routing Works in Next.js](how-routing-works-in-nextjs.md).

## Further Reading

- [Next.js App Router docs](https://nextjs.org/docs/app)
- [Next.js installation docs](https://nextjs.org/docs/app/getting-started/installation)

