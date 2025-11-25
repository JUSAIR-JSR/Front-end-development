🚀 Node.js + Express — Complete Backend Developer Course

This course teaches you everything from Node basics → Express → Middleware → MongoDB → Authentication → APIs → Deployment with real-world folder structures and projects.

📌 Table of Contents

What is Node.js

Install & Setup

Node.js Fundamentals

Express Basics

Routing

Middleware

Error Handling

Environment Variables

MongoDB + Mongoose

Controllers & Services Architecture

Authentication (JWT)

Protecting Routes

CRUD API (Users + Products Example)

File Uploads

API Validation

Pagination & Filtering

Logging

Project Structure (Enterprise Level)

Full Project: Auth + CRUD Backend

Deployment

Best Practices

Useful Commands

Bonus Section (optional expansions)

1️⃣ What is Node.js?

Node.js is a runtime that allows JavaScript to run outside the browser.

Built on Chrome V8 engine.

Perfect for: APIs, backends, real-time apps, microservices, authentication systems.

2️⃣ Install & Check Version
Install Node (LTS recommended)

Download from: https://nodejs.org

Check version:
node -v
npm -v

3️⃣ Node.js Fundamentals
Create a file:
// index.js
console.log("Hello Node");


Run it:

node index.js

Modules
const fs = require("fs");
fs.writeFileSync("test.txt", "Hello");

ES Modules

Add to package.json:

"type": "module"


Then:

import fs from "fs";

4️⃣ Express Basics

Install:

npm init -y
npm install express


Create server:

// server.js
const express = require("express");
const app = express();

app.get("/", (req, res) => res.send("API Running"));

app.listen(5000, () => console.log("Server running on port 5000"));


Run:

node server.js

5️⃣ Routing
app.get("/users", (req, res) => res.json({ message: "Users route" }));
app.post("/login", (req, res) => res.send("Login route"));


URL params:

app.get("/user/:id", (req, res) => {
  res.send(`User ID: ${req.params.id}`);
});


Query params:

app.get("/search", (req, res) => {
  res.send(`Search for: ${req.query.name}`);
});

6️⃣ Middleware

Built-in:

app.use(express.json());
app.use(express.urlencoded({ extended: true }));


Custom middleware:

function logger(req, res, next) {
  console.log(`${req.method} ${req.url}`);
  next();
}
app.use(logger);

7️⃣ Error Handling
app.use((err, req, res, next) => {
  console.error(err);
  res.status(500).json({ error: err.message });
});

8️⃣ Environment Variables

Install dotenv:

npm install dotenv


Create .env:

PORT=5000
MONGO_URI=mongodb://localhost:27017/mydb
JWT_SECRET=mysupersecret


Use in code:

require("dotenv").config();
const port = process.env.PORT;

9️⃣ MongoDB + Mongoose

Install:

npm install mongoose


Connect:

const mongoose = require("mongoose");
mongoose.connect(process.env.MONGO_URI)
  .then(()=>console.log("DB connected"))
  .catch(err=>console.log(err));


Create a model:

const userSchema = new mongoose.Schema({
  name: String,
  email: String,
  password: String,
});

const User = mongoose.model("User", userSchema);

🔟 Controllers & Services Architecture
Controller → handles request/response
Service → business logic
Model → database schema

Example Structure:

src/
 ├── controllers/
 ├── services/
 ├── models/
 ├── routes/
 ├── middlewares/
 └── server.js


Controller:

exports.createUser = async (req, res) => {
  const user = await userService.create(req.body);
  res.status(201).json(user);
};


Service:

exports.create = async (data) => {
  return await User.create(data);
};

1️⃣1️⃣ Authentication (JWT)

Install:

npm install jsonwebtoken bcryptjs


Hashing password:

const bcrypt = require("bcryptjs");

const hashed = await bcrypt.hash(password, 10);


Create token:

const jwt = require("jsonwebtoken");

const token = jwt.sign({ id: user._id }, process.env.JWT_SECRET, {
  expiresIn: "7d",
});


Login route:

if (!user) return res.status(400).json({ message: "Invalid email" });
const match = await bcrypt.compare(password, user.password);
if (!match) return res.status(400).json({ message: "Incorrect password" });

1️⃣2️⃣ Protect Routes (Auth Middleware)
function auth(req, res, next) {
  const token = req.headers.authorization?.split(" ")[1];
  if (!token) return res.status(401).json({ message: "No token" });

  try {
    req.user = jwt.verify(token, process.env.JWT_SECRET);
    next();
  } catch {
    res.status(403).json({ message: "Invalid token" });
  }
}


Use:

app.get("/me", auth, (req, res) => res.json(req.user));

1️⃣3️⃣ CRUD API Example (User + Product)
Create
app.post("/products", async (req, res) => {
  const p = await Product.create(req.body);
  res.status(201).json(p);
});

Read
app.get("/products", async (req, res) => {
  const products = await Product.find();
  res.json(products);
});

Update
app.put("/products/:id", async (req, res) => {
  const p = await Product.findByIdAndUpdate(req.params.id, req.body, { new: true });
  res.json(p);
});

Delete
app.delete("/products/:id", async (req, res) => {
  await Product.findByIdAndDelete(req.params.id);
  res.sendStatus(204);
});

1️⃣4️⃣ File Uploads (Multer)

Install:

npm install multer


Setup:

const multer = require("multer");
const upload = multer({ dest: "uploads/" });

app.post("/upload", upload.single("image"), (req, res) => {
  res.json(req.file);
});

1️⃣5️⃣ API Validation (Joi or Zod)

Install:

npm install joi


Usage:

const Joi = require("joi");

const schema = Joi.object({
  name: Joi.string().required(),
  price: Joi.number().required(),
});

const { error } = schema.validate(req.body);
if (error) return res.status(400).json({ message: error.message });

1️⃣6️⃣ Pagination & Filtering
const page = parseInt(req.query.page) || 1;
const limit = 10;
const skip = (page - 1) * limit;

const products = await Product.find().skip(skip).limit(limit);

1️⃣7️⃣ Logging

Use morgan:

npm install morgan

const morgan = require("morgan");
app.use(morgan("dev"));

1️⃣8️⃣ Project Structure (Enterprise-Level)
src/
 ├── config/
 │    └── db.js
 ├── controllers/
 ├── routes/
 ├── models/
 ├── middlewares/
 ├── services/
 ├── utils/
 ├── app.js
 └── server.js

1️⃣9️⃣ Full Project — Auth + CRUD Backend

✔ User registration
✔ Login + JWT
✔ Auth middleware
✔ Product CRUD
✔ MongoDB
✔ Validation
✔ Logging
✔ Error handling
✔ Folder structure

If you want, I can generate the full project folder with all files next.

2️⃣0️⃣ Deployment
Deploy Node on:

✔ Render
✔ Railway
✔ Cyclic
✔ VPS (Ubuntu + PM2)
✔ AWS / DigitalOcean Droplet

Build steps:

npm install
npm run build
pm2 start dist/server.js


Environment variables go in:

Render → Dashboard → Environment

Railway → Variables

VPS → .env

2️⃣1️⃣ Best Practices

✔ Always use .env
✔ Hash passwords
✔ Validate input
✔ Use controllers/services pattern
✔ Avoid business logic inside routes
✔ Use asyncHandler wrapper
✔ Use proper HTTP codes
✔ Use try/catch in async functions
✔ Paginate heavy endpoints
✔ Never store JWT in localStorage for sensitive apps
✔ Use HTTP-only cookies for auth (optional advanced)

2️⃣2️⃣ Useful Commands
npm install
npm run dev
npm start

Packages:
express
dotenv
mongoose
jsonwebtoken
bcryptjs
multer
morgan
cors
joi
nodemon


2️⃣3️⃣ Bonus Topics (Optional Add-ons)

🔥 Node.js + TypeScript version
🔥 Authentication with refresh tokens
🔥 Role-based access control (RBAC)
🔥 Image upload to Cloudinary
🔥 Email OTP verification
🔥 Socket.io (Chat App)
🔥 Real-world E-commerce API
🔥 Blog API + Comments