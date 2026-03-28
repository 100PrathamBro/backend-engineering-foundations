# Next.js Core Concepts (Interview Notes)

## File-Based Routing
Next.js uses a file-based routing system where routes are created using the folder structure inside the `app` directory.

A route works only if the folder contains a `page.tsx` file.

Example:
app/blog/page.tsx → /blog

The file name must be `page.tsx`, otherwise the route will not be created.

---

## Dynamic and Catch-All Routes
Dynamic routes are created using square brackets.

Catch-all routes are used to handle multiple nested routes.

Example:
app/blog/[...slug]/page.tsx

This can handle:
- /blog/a
- /blog/a/b
- /blog/a/b/c

---

## Layout (Reusable UI)
Next.js provides `layout.tsx` to define shared UI components.

It is used for elements like navbar, footer, and sidebar.
Layouts automatically wrap all child routes and help avoid repetition.

---

## Server Components (Default)
By default, all components in Next.js are Server Components.

They are rendered only on the server and do not send unnecessary JavaScript to the client.

Server Components can be asynchronous, which is not possible in normal React components.

Example:
`const Component = async () => {
  return <div>Server Component</div>;
};`

---

## Data Fetching (Recommended)
The recommended way to fetch data in Next.js is inside Server Components using async/await.

This improves performance and SEO because data is fetched on the server before rendering.

---

## Fetch and Caching
Next.js extends the native fetch API with caching.

By default, fetch is cached.

To disable caching:
fetch(url, { cache: "no-store" });

To enable revalidation:
fetch(url, { next: { revalidate: 60 } });

---

## Client Components
Client Components are used when interactivity is required, such as handling events or using React hooks.

To create a Client Component, add "use client" at the top of the file.

Example:
"use client";

---

## Server to Client Data Flow
Data is usually fetched in Server Components and passed to Client Components.

The Server Component creates a promise and passes it as a prop.
The Client Component resolves it using the `use()` hook and renders the data.

---

## Rendering Behavior
Server Components run only on the server.

Client Components are first rendered on the server and then hydrated on the client.

To check:
console.log("Server");
console.log("Client");

Server logs appear in the terminal, while client logs appear in the browser console.

---

## Full-Stack Capability
Next.js is a full-stack framework.

It supports both frontend development and backend APIs in the same project.

---

## API Routes
APIs are created inside the `app/api` directory.

Example:
app/api/posts/route.ts

Example code:
export async function GET() {
  return Response.json({ message: "Hello API" });
}

---

## One-Line Summary
Next.js is a full-stack React framework that uses file-based routing, Server Components by default, async data fetching on the server, Client Components for interactivity, and built-in API routing.
