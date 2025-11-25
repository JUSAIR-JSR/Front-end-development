🚀 Next.js Course — Pages Router (Complete Guide)

Target: Next.js 12 / Pages Router — file-based routing, SSR/SSG/CSR, API routes, deployment.
Use this README as Nextjs-Pages-Guide.md or README.md inside a nextjs-pages-course folder.

Table of contents

What is Next.js (Pages Router)?

Why use Pages Router (when to choose it)

Requirements (Node, npm)

Create a Next.js App (Start quickly)

Folder structure explained

Pages & Routing (file-based)

Link & Navigation

Data fetching: getStaticProps, getStaticPaths, getServerSideProps (SSG/ISR/SSR)

Client-side fetching (CSR)

API Routes (building backend endpoints)

Dynamic Routes & Catch-all routes

Head/Meta tags (next/head)

Static assets & public folder

Image optimization (next/image)

CSS & Styling (global, module CSS, Tailwind)

Environment variables

Authentication overview (simple session / JWT approach)

Incremental Static Regeneration (ISR)

Error pages & custom _error.js / _app.js / _document.js

Analytics, Performance, and SEO tips

Deployment (Vercel + other hosts)

Example Projects & Mini Projects (with instructions)

Best practices & folder conventions

Useful commands & scripts

Resources

1 — What is Next.js (Pages Router)?

Next.js is a React framework that adds:

File-based routing (Pages Router)

Server-side rendering (SSR)

Static site generation (SSG)

API routes (server code inside same repo)

Fast performance & easy deployment (Vercel)

Pages Router uses a pages/ directory. Each file becomes a route:
pages/about.js → /about

2 — Why use Pages Router?

Simpler mental model for beginners

Great for apps that rely on SSR or SSG

Built-in API routes for simple backend endpoints

Stable and widely used across many projects

3 — Requirements

Node.js (LTS recommended) — v14+ (for Next 12)

npm or yarn

Check:

node -v
npm -v

4 — Create a Next.js App (quick start)

Using create-next-app:

npx create-next-app@latest my-next-app --use-npm
# or
yarn create next-app my-next-app


Run dev server:

cd my-next-app
npm run dev
# open http://localhost:3000

5 — Folder structure (typical)
my-next-app/
 ├─ pages/
 │   ├─ api/
 │   │  └─ hello.js
 │   ├─ _app.js
 │   ├─ _document.js
 │   ├─ index.js
 │   └─ about.js
 ├─ public/
 │   └─ images/
 ├─ styles/
 │   ├─ globals.css
 │   └─ Home.module.css
 ├─ components/
 ├─ lib/
 ├─ package.json
 └─ next.config.js

6 — Pages & Routing (file-based)

pages/index.js (Home):

export default function Home() {
  return <h1>Home Page</h1>;
}


pages/about.js:

export default function About() {
  return <h1>About Page</h1>;
}


Routes auto-created: /, /about.

7 — Link & Navigation

Use next/link to navigate (client-side transitions):

import Link from 'next/link';

export default function Nav() {
  return (
    <nav>
      <Link href="/"><a>Home</a></Link>
      <Link href="/about"><a>About</a></Link>
    </nav>
  );
}


In Next 12 you must include <a> inside <Link>.

8 — Data fetching (SSG / SSR / ISR)
getStaticProps (SSG — static at build time)

Use for pages that can be pre-rendered.

// pages/posts.js
export async function getStaticProps() {
  const res = await fetch('https://jsonplaceholder.typicode.com/posts');
  const posts = await res.json();
  return { props: { posts } };
}

export default function Posts({ posts }) {
  return <>
    {posts.map(p => <div key={p.id}>{p.title}</div>)}
  </>;
}

getStaticPaths (dynamic SSG routes)
// pages/posts/[id].js
export async function getStaticPaths() {
  const res = await fetch('https://.../posts');
  const posts = await res.json();
  const paths = posts.map(p => ({ params: { id: p.id.toString() } }));
  return { paths, fallback: false };
}
export async function getStaticProps({ params }) {
  const res = await fetch(`.../posts/${params.id}`);
  const post = await res.json();
  return { props: { post } };
}

getServerSideProps (SSR — runs every request)
export async function getServerSideProps(context) {
  const res = await fetch('https://api...'); // can use cookies, headers
  const data = await res.json();
  return { props: { data } };
}

9 — Client-side fetching (CSR)

You can fetch on client using useEffect:

import { useEffect, useState } from 'react';

export default function ClientPage() {
  const [data, setData] = useState([]);
  useEffect(() => {
    fetch('/api/data').then(r=>r.json()).then(setData);
  }, []);
  return <div>{data.length}</div>;
}


Use CSR for user-specific data or interactive features.

10 — API Routes (server endpoints)

Create pages/api/hello.js:

export default function handler(req, res) {
  res.status(200).json({ message: 'Hello API' });
}


Call it from client: /api/hello.

You can implement CRUD endpoints here. Good for simple backend logic without a separate server.

11 — Dynamic Routes & Catch-all

Dynamic route file: pages/product/[slug].js → /product/phone

Catch-all: pages/docs/[...slug].js handles /docs/a/b/c.

Optional catch-all: [[...slug]].js — also matches base /.

12 — Head / Meta Tags (next/head)
import Head from 'next/head';

export default function Page() {
  return (
    <>
      <Head>
        <title>My Page</title>
        <meta name="description" content="..." />
      </Head>
      <h1>Page</h1>
    </>
  );
}

13 — Static assets & public/

Place images, favicon, robots, etc in public/.
Access via /images/logo.png.

14 — Image optimization (next/image)
import Image from 'next/image';

export default function Hero() {
  return <Image src="/images/hero.jpg" width={800} height={400} alt="hero"/>
}


Works with remote domains too (configure in next.config.js).

15 — CSS & Styling

Global CSS: import in pages/_app.js

CSS Modules: styles/Home.module.css -> import styles from '../styles/Home.module.css'

Tailwind: set up PostCSS / Tailwind and import globals.css

pages/_app.js:

import '../styles/globals.css';
export default function MyApp({ Component, pageProps }) {
  return <Component {...pageProps} />;
}

16 — Environment variables

Create .env.local:

NEXT_PUBLIC_API_URL=https://api.example.com
SECRET_API_KEY=server-only-secret


NEXT_PUBLIC_ prefix makes variable available to browser.

Server-only env vars should not have NEXT_PUBLIC_.

Use in code:

process.env.NEXT_PUBLIC_API_URL

17 — Authentication overview (simple)

Options:

Cookie-based sessions (server-auth) using libraries (next-iron-session or custom)

JWT stored in httpOnly cookie (recommended)

NextAuth.js (popular, easy social providers)

Simple flow (JWT cookie):

User logs in via API route (pages/api/login)

Backend verifies and sets Set-Cookie header with httpOnly JWT

Server-side pages (getServerSideProps) can read cookie and validate token (server-side auth)

Client fetches protected API routes (cookie sent automatically)

Example: pages/api/login.js sets res.setHeader('Set-Cookie', cookie).

18 — Incremental Static Regeneration (ISR)

getStaticProps can include revalidate:

export async function getStaticProps() {
  // build-time fetch
  return { props: { posts }, revalidate: 60 } // re-generate after 60s
}


ISR gives benefits of SSG with periodic updates.

19 — Error pages & custom _error.js, _app.js, _document.js

_app.js — wraps pages (global state, layout)

_document.js — custom HTML document (rare; for fonts or lang)

_error.js — custom error page

Example _app.js:

import '../styles/globals.css';
export default function App({ Component, pageProps }) {
  return <Component {...pageProps} />;
}

20 — Analytics, Performance & SEO Tips

Use image optimization (next/image)

Avoid blocking large JavaScript on first load

Use getStaticProps where possible

Add meta tags and Open Graph data via next/head

Enable gzip/brotli on host (Vercel handles)

Use Lighthouse to audit page performance and SEO

21 — Deployment
Deploy to Vercel (recommended)

Push repo to GitHub.

Sign in to Vercel and import project.

Vercel auto-detects Next.js and sets build command: npm run build (next build) and output.

Build locally:

npm run build
npm start


If using serverless API routes, Vercel handles them.

Other hosts

Netlify (with adapter)

DigitalOcean App Platform

Dockerized deployment (use next start on Node server)