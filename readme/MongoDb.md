🍃 MongoDB — Complete Beginner to Advanced Course

(Full README)

📌 Table of Contents

What is MongoDB?

Install MongoDB

Mongo Shell Basics

Create Database

Create Collection

Insert Documents

Query Documents

Operators ($gt, $lt, $in, $and, $or, $not)

Update Documents

Delete Documents

Projection (select fields)

Sorting

Limit & Skip

Indexes

Data Types

Embedded Documents

Arrays

Aggregation Pipeline

$match, $group, $sort, $project

Relationships (Refs vs Embedded)

MongoDB Compass

Mongoose (Node.js ODM)

Schema & Models

CRUD with Mongoose

Validations

Middleware (pre, post hooks)

Populate (joins)

MongoDB with Express (API)

MongoDB Backup/Restore

Advanced Topics

MongoDB Atlas (Cloud)

Final Projects

1️⃣ What is MongoDB?

MongoDB is a NoSQL document database, storing data as JSON-like documents.

Used by:

✔ Node.js
✔ MERN stack
✔ Mobile apps
✔ Real-time apps
✔ Scalable cloud apps

2️⃣ Install MongoDB

Download:
https://www.mongodb.com/try/download/community

Check version:

mongod --version

3️⃣ MongoDB Shell

Start shell:

mongo

4️⃣ Create Database
use school


Show db:

show dbs

5️⃣ Create Collection
db.createCollection("students")


Show collections:

show collections

6️⃣ Insert Documents
db.students.insertOne({
  name: "John",
  age: 20,
  course: "Math"
})


Insert many:

db.students.insertMany([
  { name: "A", age: 22 },
  { name: "B", age: 25 }
])

7️⃣ Query Documents
db.students.find()


Pretty print:

db.students.find().pretty()

8️⃣ Operators
Greater than:
db.students.find({ age: { $gt: 20 } })


Less than:

db.students.find({ age: { $lt: 20 } })


In list:

db.students.find({ age: { $in: [18, 20, 22] } })


AND:

db.students.find({ age: { $gt: 18 }, course: "Math" })


OR:

db.students.find({
  $or: [{ age: 18 }, { age: 22 }]
})


NOT:

db.students.find({ age: { $not: { $eq: 20 } } })

9️⃣ Update Documents

Set values:

db.students.updateOne({ name: "John" }, { $set: { age: 30 } })


Add field:

db.students.updateOne({ name: "John" }, { $set: { country: "India" } })


Increment:

db.students.updateOne({ name: "John" }, { $inc: { age: 1 } })


Update many:

db.students.updateMany({}, { $set: { approved: true } })

🔟 Delete Documents

Delete one:

db.students.deleteOne({ name: "John" })


Delete many:

db.students.deleteMany({ age: { $gt: 25 } })


Drop collection:

db.students.drop()

1️⃣1️⃣ Projection (Select specific fields)
db.students.find({}, { name: 1, age: 1 })


Hide _id:

db.students.find({}, { _id: 0, name: 1 })

1️⃣2️⃣ Sort
db.students.find().sort({ age: 1 })   // ASC
db.students.find().sort({ age: -1 })  // DESC

1️⃣3️⃣ Limit & Skip
db.students.find().limit(5)
db.students.find().skip(10)

1️⃣4️⃣ Index
db.students.createIndex({ name: 1 })


Show indexes:

db.students.getIndexes()

1️⃣5️⃣ Data Types
Type	Example
String	"John"
Number	25
Boolean	true
Array	[1,2,3]
Object	{ a:1 }
Date	new Date()
Null	null
1️⃣6️⃣ Embedded Documents
db.students.insertOne({
  name: "John",
  address: {
    city: "Delhi",
    pin: 110011
  }
})

1️⃣7️⃣ Arrays
db.students.insertOne({
  name: "A",
  hobbies: ["cricket", "music"]
})


Query array element:

db.students.find({ hobbies: "music" })

1️⃣8️⃣ Aggregation Pipeline
Example:
db.students.aggregate([
  { $match: { age: { $gt: 18 } } },
  { $group: { _id: "$course", count: { $sum: 1 } } },
  { $sort: { count: -1 } }
])

1️⃣9️⃣ Relationships: Referencing vs Embedding
Referencing (like JOIN):
db.books.insertOne({ title: "JS", authorId: 1 })
db.authors.insertOne({ _id: 1, name: "John" })

Embedding:
{
  title: "JS",
  author: { name: "John", age: 30 }
}

2️⃣0️⃣ MongoDB Compass (GUI)

Download GUI:
https://www.mongodb.com/try/download/compass

2️⃣1️⃣ Mongoose (Node.js ODM)

Install:

npm install mongoose


Connect:

import mongoose from "mongoose";

mongoose.connect("mongodb://localhost:27017/school")

2️⃣2️⃣ Schema & Model
const studentSchema = new mongoose.Schema({
  name: String,
  age: Number,
  email: String
});

const Student = mongoose.model("Student", studentSchema);

2️⃣3️⃣ CRUD with Mongoose
Create:
await Student.create({ name: "John", age: 20 });

Read:
await Student.find();

Update:
await Student.updateOne({ name: "John" }, { age: 30 });

Delete:
await Student.deleteOne({ name: "John" });

2️⃣4️⃣ Validations
const studentSchema = new mongoose.Schema({
  name: { type: String, required: true },
  age: { type: Number, min: 5 },
  email: { type: String, match: /@/ }
});

2️⃣5️⃣ Middleware (Hooks)
studentSchema.pre("save", function(next) {
  console.log("Saving...");
  next();
});

2️⃣6️⃣ Populate (joins)
Student.find().populate("department");

2️⃣7️⃣ MongoDB + Express API
app.get("/students", async (req, res) => {
  const data = await Student.find();
  res.json(data);
});

2️⃣8️⃣ Backup & Restore
Backup:
mongodump --db=school --out=backup/

Restore:
mongorestore --db=school backup/school

2️⃣9️⃣ MongoDB Atlas (Cloud)

https://www.mongodb.com/atlas

✔ Free cloud database
✔ Connection string
✔ Scalable
✔ Dashboard