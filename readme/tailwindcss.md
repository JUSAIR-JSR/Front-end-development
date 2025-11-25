# Tailwind CSS — Full Complete Course (Beginner to Advanced)

This guide upgrades your Tailwind CSS course into a **complete learning module**, covering:

✅ Setup (CDN + CLI + Frameworks)
✅ Configuration (theme, colors, fonts, shadows, animations, screens)
✅ Utility classes (spacing, flexbox, grid, borders, backgrounds…)
✅ Components (buttons, cards, navbar, forms)
✅ Responsive design
✅ Dark Mode
✅ Reusable Components (using @apply)

---

# ⭐ 1. How to Setup Tailwind CSS in HTML

## **Step 1: Install Tailwind CSS**

```
npm install -D tailwindcss
```

```
npx tailwindcss init
```

## **Step 2: Configure Tailwind Paths in `tailwind.config.js`**

```
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["*.html"],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

## **Step 3: Create your main input CSS file**

File: **src/input.css**

```
@tailwind base;
@tailwind components;
@tailwind utilities;
```

## **Step 4: Build your CSS**

```
npx tailwindcss -i ./src/input.css -o ./src/output.css --watch
```

## **Step 5: Add output.css to your HTML**

```
<!doctype html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link href="./output.css" rel="stylesheet">
</head>
<body>
  <h1 class="text-3xl font-bold underline">Hello world!</h1>
</body>
</html>
```

---

# ⭐ 2. Setup Tailwind CSS using CDN (Quick Demo)

Use this for fast prototypes:

```
<script src="https://cdn.tailwindcss.com"></script>
```

Add custom config inline:

```
<script>
  tailwind.config = {
    theme: {
      extend: {
        colors: {
          brand: '#00d0ff'
        }
      }
    }
  }
</script>
```

---

# ⭐ 3. Tailwind Folder Structure (Recommended)

```
project/
 ├─ src/
 │   └─ input.css
 ├─ dist/
 │   └─ output.css
 ├─ index.html
 └─ tailwind.config.js
```

---

# ⭐ 4. Tailwind Core Concepts

## **Utility-First Classes**

Everything is a class:

```
<p class="text-gray-500 text-lg p-4 bg-black"></p>
```

## **Responsive Prefixes**

```
text-lg md:text-2xl lg:text-4xl
```

## **State Variants**

```
hover:bg-blue-500 focus:ring-2 active:scale-95
```

## **Dark Mode**

Enable in config:

```
darkMode: 'class'
```

Activate:

```
<html class="dark">
```

---

# ⭐ 5. Spacing (margin + padding)

```
mt-4 mb-2 ml-1 mx-4
p-2 px-6 py-4
```

Examples:

```
<div class="p-4 m-4 bg-gray-800"></div>
```

---

# ⭐ 6. Colors

```
text-red-500
bg-blue-600
border-green-400
```

Custom colors:

```
extend: {
  colors: {
    neon: '#00f7ff'
  }
}
```

---

# ⭐ 7. Typography

```
text-sm text-lg text-4xl
font-bold font-light
tracking-wide leading-loose
```

Example:

```
<h1 class="text-4xl font-extrabold tracking-tight">Heading</h1>
```

---

# ⭐ 8. Flexbox

```
flex
flex-col flex-row
items-center justify-between
```

Example:

```
<div class="flex items-center justify-between p-4"></div>
```

---

# ⭐ 9. Grid

```
grid grid-cols-2 grid-cols-4
gap-4
```

Example:

```
<div class="grid grid-cols-3 gap-4"></div>
```

---

# ⭐ 10. Borders & Radius

```
border border-2 border-blue-500
rounded rounded-lg rounded-full
```

---

# ⭐ 11. Shadows

```
shadow
shadow-lg
shadow-xl
```

Custom:

```
extend: {
  boxShadow: {
    neon: '0 0 20px #00eaff'
  }
}
```

---

# ⭐ 12. Backgrounds

```
bg-red-500
bg-gradient-to-r from-blue-500 to-purple-600
bg-cover bg-center
```

---

# ⭐ 13. Width & Height

```
w-10 w-1/2 w-full
h-10 h-screen
```

---

# ⭐ 14. Positioning

```
absolute relative fixed sticky
top-0 left-4 z-50
```

---

# ⭐ 15. Transitions & Animations

```
transition
duration-300 ease-in-out
hover:scale-105
```

Custom animation:

```
extend: {
  keyframes: {
    spinSlow: { '0%': {transform: 'rotate(0deg)'}, '100%': {transform: 'rotate(360deg)'} }
  },
  animation: {
    spinSlow: 'spinSlow 4s linear infinite'
  }
}
```

---

# ⭐ 16. Tailwind Components (@apply)

```
.btn {
  @apply px-4 py-2 bg-blue-600 text-white rounded shadow;
}
```

Use in HTML:

```
<button class="btn">Click</button>
```

---

# ⭐ 17. Common Tailwind UI Patterns

## **Button**

```
<button class="px-4 py-2 bg-blue-600 text-white rounded">Click</button>
```

## **Card**

```
<div class="p-6 bg-gray-900 rounded-xl shadow-lg">
  <h2 class="text-xl font-bold">Title</h2>
  <p class="text-gray-300">Description here.</p>
</div>
```

## **Navbar**

```
<nav class="flex justify-between p-4 bg-gray-800 text-white">
  <a>Logo</a>
  <ul class="flex gap-4">
    <li>Home</li>
    <li>About</li>
  </ul>
</nav>
```

## **Form**

```
<input class="p-2 border rounded w-full">
```

---

# ⭐ 18. Plugins

```
@tailwindcss/forms
@tailwindcss/typography
@tailwindcss/aspect-ratio
```

Enable:

```
plugins: [require('@tailwindcss/forms')]
```

---

