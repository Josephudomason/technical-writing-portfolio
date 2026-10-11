| Field | Details |
| --- | --- |
| Title | How Routing Works in Next.js |
| Description | Understand file-based routing, layouts, dynamic routes, and navigation in the Next.js App Router. |
| Category | React / Next.js |
| Audience | Beginner developers |
| Difficulty | Beginner |

# How Routing Works in Next.js

Next.js uses file-based routing. In the App Router, the folder structure inside `app` defines the URL structure of your application.

## Prerequisites

- A basic Next.js project from [Getting Started With Next.js](getting-started-with-nextjs.md)
- Basic React components
- Comfort creating files and folders

## What Is File-Based Routing?

File-based routing means routes are created by files and folders instead of a separate route configuration object. A folder represents a route segment. A `page.tsx` file makes that segment publicly accessible.

## Why Routing Matters

File-based routing keeps navigation structure close to the code it renders. Developers can scan the `app` directory and understand which URLs exist, which layouts wrap them, and which segments are dynamic.

## How It Works

`app/page.tsx` maps to `/`. `app/about/page.tsx` maps to `/about`. Dynamic segments use square brackets, such as `app/blog/[slug]/page.tsx`. Shared UI lives in `layout.tsx` files.

## Example

This structure creates a home page, an about page, and dynamic blog post pages.

```text
app/
  layout.tsx
  page.tsx
  about/
    page.tsx
  blog/
    [slug]/
      page.tsx
```

The `[slug]` folder captures values such as `/blog/first-post`. In the route component, the `params` value contains the dynamic segment.

## Common Mistakes

- Creating a folder but forgetting the `page.tsx` file.
- Using Pages Router examples such as `pages/api` when working in an App Router article.
- Confusing layouts with pages.
- Using regular `<a>` tags for internal navigation when `next/link` is more appropriate.

## Best Practices

- Use `Link` from `next/link` for internal navigation.
- Keep route folders organized around user-facing URLs.
- Use dynamic segments for IDs, slugs, and other variable path values.
- Use route groups when you need organization without changing the URL.

## Troubleshooting

If a URL is missing, confirm that each public route segment ends with a `page.tsx` file. If navigation reloads the full page, check that internal links use the `Link` component.

## What to Remember

In the App Router, folders are part of the user-facing URL design. Keep route structure predictable, use dynamic segments for values such as IDs or slugs, and reserve layouts for UI that should persist across related pages.

## Next Steps

- Read [Server Components vs Client Components](server-components-vs-client-components.md) to understand where route UI executes.
- Connect routes to data with [Supabase](../04-developer-tools/getting-started-with-supabase.md) or [Prisma](../04-developer-tools/prisma-beginners-guide.md).

## Further Reading

- [Next.js Layouts and Pages](https://nextjs.org/docs/app/getting-started/layouts-and-pages)
- [Next.js Linking and Navigating](https://nextjs.org/docs/app/getting-started/linking-and-navigating)

