# React.js Course (Beginner to Advanced)

Welcome to the **React.js Complete Course Readme**! 🚀
This guide introduces you to React from basics to advanced concepts.

---

## 📌 What You Will Learn

* What is React?
* Create React App / Vite Setup
* JSX
* Components (Functional & Class)
* Props & State
* Event Handling
* Conditional Rendering
* Lists & Keys
* Forms & Controlled Inputs
* useEffect & useState Hooks
* useRef, useMemo, useCallback
* React Router
* Context API
* API Calls (fetch / axios)
* Folder Structure & Best Practices
* Mini Projects

---

## ⭐ 1. What is React?

React is a **JavaScript library** for building **user interfaces**. It is component-based and allows fast rendering using the Virtual DOM.

---

## ⭐ 2. Create a React Project

### Option A — Using **Vite** (recommended)

```
npm create vite@latest my-app --template react
cd my-app
npm install
npm run dev
```

### Option B — Using **Create React App**

```
npx create-react-app my-app
cd my-app
npm start
```

---

## ⭐ 3. Folder Structure

```
my-app/
 ├─ src/
 │   ├─ App.jsx
 │   ├─ main.jsx
 │   ├─ components/
 │   └─ assets/
 ├─ index.html
 └─ package.json
```

---

## ⭐ 4. JSX

JSX lets you write HTML inside JavaScript.

```
function App() {
  return <h1>Hello React!</h1>;
}
```

---

## ⭐ 5. Components

### Functional Component

```
function Hello() {
  return <h2>Hello Component!</h2>;
}
export default Hello;
```

### Using it in App.jsx

```
import Hello from './Hello';

function App() {
  return <Hello />;
}

export default App;
```

---

## ⭐ 6. Props

```
function Welcome(props) {
  return <h2>Welcome {props.name}</h2>;
}

function App() {
  return <Welcome name="Jusair" />;
}
```

---

## ⭐ 7. useState Hook

```
import { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <h1>{count}</h1>
      <button onClick={() => setCount(count + 1)}>+</button>
    </div>
  );
}
```

---

## ⭐ 8. useEffect Hook

```
useEffect(() => {
  console.log("Component Loaded");
}, []);
```

---

## ⭐ 9. Lists & Keys

```
const items = ["Apple", "Banana", "Orange"];

function App() {
  return (
    <ul>
      {items.map((x, i) => <li key={i}>{x}</li>)}
    </ul>
  );
}
```

---

## ⭐ 10. Forms

```
function Form() {
  const [name, setName] = useState("");

  return (
    <div>
      <input value={name} onChange={(e) => setName(e.target.value)} />
      <p>{name}</p>
    </div>
  );
}
```

---

## ⭐ 11. React Router

Install:

```
npm install react-router-dom
```

Example:

```
import { BrowserRouter, Routes, Route } from 'react-router-dom';

function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/about" element={<About />} />
      </Routes>
    </BrowserRouter>
  );
}
```

---

## ⭐ 12. Fetch API / Axios

```
useEffect(() => {
  fetch("https://jsonplaceholder.typicode.com/users")
    .then(res => res.json())
    .then(data => console.log(data));
}, []);
```

Or using axios:

```
npm install axios
```

```
axios.get(url).then(res => console.log(res.data));
```

---

## ⭐ 13. Context API

```
const UserContext = createContext();

function App() {
  return (
    <UserContext.Provider value={{ name: "Jusair" }}>
      <Home />
    </UserContext.Provider>
  );
}
```


---

## ⭐ Mini Project: To-Do App

A simple and powerful React To-Do list application using **useState**.

### 📌 Full Source Code

```jsx
import { useState } from "react";

function TodoApp() {
  const [task, setTask] = useState("");
  const [todos, setTodos] = useState([]);

  const addTask = () => {
    if (task.trim() === "") return;
    setTodos([...todos, task]);
    setTask("");
  };

  const removeTask = (index) => {
    setTodos(todos.filter((_, i) => i !== index));
  };

  return (
    <div style={{ maxWidth: "400px", margin: "20px auto" }}>
      <h2>To-Do App</h2>

      <input
        value={task}
        onChange={(e) => setTask(e.target.value)}
        placeholder="Enter a task"
        style={{ padding: "8px", width: "100%" }}
      />

      <button onClick={addTask} style={{ marginTop: "10px", padding: "8px", width: "100%" }}>
        Add Task
      </button>

      <ul style={{ marginTop: "20px" }}>
        {todos.map((t, index) => (
          <li key={index} style={{ display: "flex", justifyContent: "space-between", marginBottom: "10px" }}>
            {t}
            <button onClick={() => removeTask(index)} style={{ color: "red" }}>X</button>
          </li>
        ))}
      </ul>
    </div>
  );
}

export default TodoApp;
```

---

### 📌 How to use it

1. Create a file: `TodoApp.jsx`
2. Paste the code
3. Import it inside **App.jsx**:

```jsx
import TodoApp from "./TodoApp";

function App() {
  return <TodoApp />;
}

export default App;
```

---

### ⭐ Features

* Add tasks
* Delete tasks
* Stores tasks in React state
* Auto UI re-render on every update

---

