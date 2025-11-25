TypeScript Course — Complete (TypeScript + React + Node)

Goal: Learn TypeScript from zero to production-ready: basics → advanced types → using TypeScript with React → building an Express API with TypeScript → full To-Do app (frontend + backend) → testing & deployment.

Table of contents

Why TypeScript?

Install & Setup (CLI + config)

Basic Types & Syntax

Functions & Typing

Interfaces & Type Aliases

Unions, Intersections & Literal Types

Generics

Utility Types (Partial, Pick, Omit, Record, ReturnType...)

Advanced Types (Mapped types, Conditional types, Type inference)

Modules & Namespaces

Tooling (tsconfig, ESLint, Prettier, ts-node, nodemon)

TypeScript + React (tsx, props, hooks, events, typing refs)

TypeScript + Node/Express (server, routes, controllers, models)

Mini Project: To-Do App (React + TS + Express + TS backend)

Testing (Jest + ts-jest)

Deployment & Build Tips

Best Practices & Folder Structures

Resources

1 — Why TypeScript?

Superset of JavaScript → adds static types.

Catches many bugs at compile time.

Improves editor autocompletion & refactorability.

Widely used in production (React, Node, Next.js, backend).

2 — Install & Setup
Global / quick install
npm init -y
npm install --save-dev typescript
npx tsc --init

tsconfig.json (recommended starting)
{
  "compilerOptions": {
    "target": "ES2020",
    "module": "commonjs",
    "lib": ["ES2020", "DOM"],
    "outDir": "dist",
    "rootDir": "src",
    "strict": true,
    "esModuleInterop": true,
    "skipLibCheck": true,
    "forceConsistentCasingInFileNames": true,
    "moduleResolution": "node",
    "resolveJsonModule": true,
    "noImplicitAny": true,
    "sourceMap": true
  },
  "include": ["src"],
  "exclude": ["node_modules", "dist"]
}

Helpful dev packages
npm i -D ts-node-dev @types/node typescript
# For React projects:
npm i -D vite @types/react @types/react-dom
# For Node express:
npm i express
npm i -D @types/express

3 — Basic Types & Syntax
// src/index.ts
let name: string = "Jusair";
let age: number = 25;
let isActive: boolean = true;
let anything: any = 10; // avoid `any` when possible

// arrays
let nums: number[] = [1,2,3];
let names: Array<string> = ["a","b"];

// tuple
let person: [string, number] = ["Jusair", 21];

// enum
enum Role { Admin, User, Guest }
const r: Role = Role.Admin;


null / undefined vs void:

function log(message: string): void {
  console.log(message);
}

4 — Functions & Typing
function add(a: number, b: number): number {
  return a + b;
}

const multiply = (x: number, y: number): number => x * y;

function greet(name: string = "Guest"): string {
  return `Hello ${name}`;
}

// function type
let fn: (a: number, b: number) => number;
fn = add;


Optional & rest parameters:

function join(separator: string, ...parts: string[]): string {
  return parts.join(separator);
}

5 — Interfaces & Type Aliases

Interface

interface User {
  id: number;
  name: string;
  email?: string; // optional
}

function show(user: User) { console.log(user.name); }


Type Alias

type ID = string | number;
type Point = { x: number; y: number };


Use interface for objects/shape; type for unions, tuples, complex types.

6 — Unions, Intersections & Literal Types
type Status = "pending" | "success" | "error";

function handle(status: Status) {
  if (status === "success") { /*...*/ }
}

type A = { a: number };
type B = { b: string };
type C = A & B; // intersection {a:number, b:string}


Narrowing:

function print(input: string | number) {
  if (typeof input === "string") console.log(input.toUpperCase());
  else console.log(input.toFixed(2));
}

7 — Generics
function identity<T>(arg: T): T {
  return arg;
}
const s = identity<string>("hello");

interface ApiResponse<T> {
  data: T;
  status: number;
}


Generic constraints:

function getLength<T extends { length: number }>(x: T) {
  return x.length;
}

8 — Utility Types

Partial<T> — make properties optional

Required<T> — opposite of partial

Pick<T, K> — select keys

Omit<T, K> — remove keys

Record<K,T> — map keys to type

ReturnType<T> — get function return type

Examples:

type UserUpdate = Partial<User>;
type UserPreview = Pick<User, "id" | "name">;
type MapOfIds = Record<string, number>;

9 — Advanced Types

Mapped Types:

type Readonly<T> = { readonly [K in keyof T]: T[K] }


Conditional Types:

type MyType<T> = T extends string ? string[] : number[];


infer keyword — used in conditional types for extracting types.

10 — Modules & ES Module Interop

export / import usage:

export function add() {}
// in other file
import { add } from './math';


Use esModuleInterop and allowSyntheticDefaultImports in tsconfig for default imports of CJS modules.

11 — Tooling
ESLint + Prettier
npm i -D eslint @typescript-eslint/parser @typescript-eslint/eslint-plugin


.eslintrc.js basic:

module.exports = {
  parser: '@typescript-eslint/parser',
  plugins: ['@typescript-eslint'],
  extends: ['eslint:recommended','plugin:@typescript-eslint/recommended'],
};

ts-node-dev (dev server)
npm i -D ts-node-dev
# package.json script:
"dev": "ts-node-dev --respawn --transpile-only src/index.ts"

12 — TypeScript + React
Create with Vite (recommended)
npm create vite@latest my-app --template react-ts
cd my-app
npm install
npm run dev

Basic TSX Component
// src/components/Hello.tsx
import React from 'react';

type Props = { name: string };

const Hello: React.FC<Props> = ({ name }) => {
  return <h1>Hello {name}</h1>;
};

export default Hello;

useState typing
const [count, setCount] = React.useState<number>(0);
const [todos, setTodos] = React.useState<string[]>([]);

Event typing
function handleChange(e: React.ChangeEvent<HTMLInputElement>) {
  console.log(e.target.value);
}

Refs
const inputRef = React.useRef<HTMLInputElement | null>(null);

Props with children
type CardProps = { title: string; children?: React.ReactNode };

Context with Types
type AuthContextType = { user: User | null, login: (u: User) => void };
const AuthContext = React.createContext<AuthContextType | undefined>(undefined);

13 — TypeScript + Node/Express
Setup
npm i express
npm i -D typescript ts-node-dev @types/express

Basic Express server (TS)
// src/server.ts
import express, { Request, Response } from 'express';

const app = express();
app.use(express.json());

app.get('/api/ping', (req: Request, res: Response) => {
  res.json({ pong: true });
});

app.listen(4000, () => console.log('Server running on :4000'));

Types for request body/params
app.post('/users', (req: Request<{}, {}, CreateUserDto>, res: Response) => {
  // req.body typed as CreateUserDto
});

Example DTO & model types
type CreateUserDto = {
  name: string;
  email: string;
}

Using Mongoose with TS (tip)

Use typed models and lean() where possible. Install @types/mongoose and create interfaces for schema.

14 — Mini Project: To-Do App (React + TS frontend + Express TS backend)
Folder structure (full project)
project/
  client/         # React + TS (Vite)
  server/         # Express + TS

Server (Express + TS) — minimal API

server/src/index.ts

import express from 'express';
import cors from 'cors';
import { v4 as uuid } from 'uuid';

const app = express();
app.use(cors());
app.use(express.json());

type Todo = { id: string; title: string; done: boolean };
let todos: Todo[] = [];

app.get('/api/todos', (req, res) => res.json(todos));

app.post('/api/todos', (req, res) => {
  const { title } = req.body as { title: string };
  const todo: Todo = { id: uuid(), title, done: false };
  todos.push(todo);
  res.status(201).json(todo);
});

app.delete('/api/todos/:id', (req, res) => {
  todos = todos.filter(t => t.id !== req.params.id);
  res.status(204).send();
});

app.patch('/api/todos/:id', (req, res) => {
  const id = req.params.id;
  const todo = todos.find(t => t.id === id);
  if (!todo) return res.status(404).send();
  todo.done = !todo.done;
  res.json(todo);
});

app.listen(4000, () => console.log('API listening on :4000'));


Run server:

cd server
npm i
npm run dev # script: ts-node-dev

Client (React + TS) — minimal usage

client/src/App.tsx

import React, { useEffect, useState } from 'react';

type Todo = { id: string; title: string; done: boolean };

export default function App() {
  const [todos, setTodos] = useState<Todo[]>([]);
  const [title, setTitle] = useState('');

  useEffect(() => {
    fetch('http://localhost:4000/api/todos').then(r => r.json()).then(setTodos);
  }, []);

  async function addTodo() {
    if (!title.trim()) return;
    const res = await fetch('http://localhost:4000/api/todos', {
      method: 'POST',
      headers: {'Content-Type':'application/json'},
      body: JSON.stringify({ title })
    });
    const newTodo = await res.json();
    setTodos(prev => [newTodo, ...prev]);
    setTitle('');
  }

  async function toggle(id: string) {
    const res = await fetch(`http://localhost:4000/api/todos/${id}`, { method: 'PATCH' });
    const updated = await res.json();
    setTodos(prev => prev.map(t => t.id === id ? updated : t));
  }

  async function remove(id: string) {
    await fetch(`http://localhost:4000/api/todos/${id}`, { method: 'DELETE' });
    setTodos(prev => prev.filter(t => t.id !== id));
  }

  return (
    <div style={{ maxWidth: 600, margin: '3rem auto' }}>
      <h1>To-Do (TS)</h1>
      <div>
        <input value={title} onChange={(e)=>setTitle(e.target.value)} />
        <button onClick={addTodo}>Add</button>
      </div>
      <ul>
        {todos.map(todo => (
          <li key={todo.id}>
            <input type="checkbox" checked={todo.done} onChange={()=>toggle(todo.id)} />
            {todo.title}
            <button onClick={()=>remove(todo.id)}>x</button>
          </li>
        ))}
      </ul>
    </div>
  );
}

15 — Testing (Jest + ts-jest)

Install:

npm i -D jest ts-jest @types/jest
npx ts-jest config:init


Sample test:

// sum.ts
export const sum = (a:number,b:number) => a+b;

// sum.test.ts
import { sum } from './sum';
test('sum', ()=> {
  expect(sum(1,2)).toBe(3);
});


Run tests:

npm test

16 — Deployment & Build Tips

Build React (Vite): npm run build → deploy dist/ to Netlify, Vercel, GitHub Pages.

Build Node: transpile tsc → start Node with node dist/index.js or use pm2.

Don’t include devDependencies in production.

Use environment variables for keys (dotenv).

For typesafety in production, use strict mode and run tsc --noEmit in CI to type-check only.

17 — Best Practices & Folder Structures
Simple Node project
src/
  controllers/
  routes/
  models/
  services/
  index.ts
tsconfig.json
package.json

React project
src/
  components/
  pages/
  hooks/
  services/
  types/
  App.tsx
  main.tsx


Best practices:

Enable strict in tsconfig.

Use small modular types & reuse them (central types/ folder).

Prefer unknown over any. Validate unknown.

Use linting & formatting.

Use type vs interface consistently (interface for objects; type for unions).

Keep DTOs (request/response types) separate from domain models.

18 — Extra Topics (Optional expansions)

TypeScript with GraphQL (Apollo)

TypeScript + Next.js (SSG/SSR)

TypeScript + Prisma (ORM & types)

Type-safe React Query caches

Monorepos with TS (pnpm/lerna/turborepo)

Advanced types: recursive types, nominal typing hacks

19 — Useful Commands Summary
# init
npm init -y
npm i -D typescript ts-node-dev @types/node

# run TypeScript node server
npx ts-node-dev --respawn src/index.ts

# compile
npx tsc

# react vite
npm create vite@latest client --template react-ts
cd client
npm install
npm run dev

20 — Example tsconfig for React (Vite)
{
  "compilerOptions": {
    "target": "ES2020",
    "lib": ["DOM","ES2020"],
    "jsx": "react-jsx",
    "module": "ESNext",
    "moduleResolution":"node",
    "strict": true,
    "esModuleInterop": true,
    "skipLibCheck": true,
    "forceConsistentCasingInFileNames": true,
    "resolveJsonModule": true,
    "isolatedModules": true,
    "noEmit": true
  },
  "include": ["src"]
}
