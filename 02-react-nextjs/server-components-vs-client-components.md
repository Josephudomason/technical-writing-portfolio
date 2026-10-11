| Field | Details |
| --- | --- |
| Title | Next.js Server Components vs Client Components |
| Description | Learn when to use Server Components and Client Components in the Next.js App Router. |
| Category | React / Next.js |
| Audience | Beginner developers |
| Difficulty | Beginner |

# Next.js Server Components vs Client Components

In the Next.js App Router, the first question to ask about a component is simple: does this need to run in the browser? If the answer is no, it can usually stay as a Server Component. If the answer is yes, it probably needs to be a Client Component.

## Prerequisites

- Basic React components from [How React Components Work](how-react-components-work.md)
- A Next.js App Router project
- Basic understanding of client and server environments

## What Are Server and Client Components?

A Server Component renders on the server and can safely access server-side resources such as databases and private environment variables. A Client Component is included in the browser JavaScript bundle and can use interactivity features such as `useState`, `useEffect`, and click handlers.

## Why the Boundary Matters

The boundary affects performance, security, and how you organize code. Server Components can keep database access and private environment variables on the server. Client Components are still necessary for interaction, but they add browser JavaScript, so you usually want them to be as small and focused as practical.

## How It Works

In the App Router, files are Server Components unless they start with the `"use client"` directive. Once a file is marked as a Client Component, its imports become part of the client component tree. Props passed from Server Components to Client Components must be serializable.

## Example

This example keeps data loading on the server and moves only the click behavior into a small client component.

```tsx
// app/products/page.tsx
import AddToCartButton from "./add-to-cart-button";

export default async function ProductsPage() {
  const products = await getProductsFromDatabase();

  return (
    <main>
      {products.map((product) => (
        <section key={product.id}>
          <h2>{product.name}</h2>
          <AddToCartButton productId={product.id} />
        </section>
      ))}
    </main>
  );
}

// app/products/add-to-cart-button.tsx
"use client";

export default function AddToCartButton({ productId }) {
  return <button onClick={() => console.log(productId)}>Add to cart</button>;
}
```

`ProductsPage` can fetch from the database because it is a Server Component. `AddToCartButton` is a Client Component because it handles a click event.

## Common Mistakes

- Adding `use client` to entire pages when only a small widget needs interactivity.
- Passing functions or class instances from a Server Component to a Client Component.
- Using browser APIs such as `window` in a Server Component.
- Exposing private API keys to client code.

## Best Practices

- Keep data fetching and secrets in Server Components when possible.
- Move only interactive UI into Client Components.
- Pass plain serializable props such as strings, numbers, booleans, arrays, and objects.
- Use clear file names for client-only widgets.

## Troubleshooting

If you see an error about event handlers or hooks in a Server Component, move that logic into a Client Component. If serialization fails, inspect the props crossing the server-client boundary.

## What to Remember

Start with Server Components and add `use client` only where the UI needs browser behavior. That habit keeps data fetching close to the server, limits accidental secret exposure, and makes interactive pieces easier to find during code review.

## Next Steps

- Learn App Router files in [How Routing Works in Next.js](how-routing-works-in-nextjs.md).
- Review state in [Props vs State in React](props-vs-state-in-react.md).

## Further Reading

- [Next.js Server and Client Components](https://nextjs.org/docs/app/getting-started/server-and-client-components)
- [Next.js use client directive](https://nextjs.org/docs/app/api-reference/directives/use-client)

