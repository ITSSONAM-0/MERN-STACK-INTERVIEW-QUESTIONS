# 🟢 1. What is MongoDB?
Answer:
MongoDB is a NoSQL, document-based database that stores data in JSON-like BSON format.

Example document:
```
{
  "_id": 1,
  "name": "Sonam",
  "skills": ["Java", "React"],
  "experience": 1
}
```
# 🟢 2. SQL vs NoSQL (MongoDB)
| SQL              | MongoDB                 |
| ---------------- | ----------------------- |
| Tables & rows    | Collections & documents |
| Fixed schema     | Schema-less             |
| Joins            | Embedded / Lookup       |
| Vertical scaling | Horizontal scaling      |

# 🟡 3. CRUD Operations (Very Common)
➕ Insert
```
db.users.insertOne({ name: "Sonam", age: 22 })
```
📖 Read
```
db.users.find({ age: { $gt: 18 } })
```
✏ Update
```
db.users.updateOne(
  { name: "Sonam" },
  { $set: { age: 23 } }
)
```
❌ Delete
```
db.users.deleteOne({ name: "Sonam" })
```
# 🟠 4. What is BSON?
Answer:
Binary JSON → faster storage + supports extra data types (Date, ObjectId).

Example:
```
{
  _id: ObjectId("64ab..."),
  createdAt: ISODate("2025-01-24")
}
```
# 🟠 5. Query Operators
Comparison
```
db.users.find({ age: { $gte: 18 } })
```
Logical
```
db.users.find({
  $and: [{ age: { $gt: 18 } }, { city: "Delhi" }]
})
```
Regex
```
db.users.find({ name: { $regex: "^S" } })
```
# 🔵 6. Indexing
What is Index?

Answer:
Index improves query speed by avoiding full collection scan.

Create Index
```
db.users.createIndex({ email: 1 })
```
Compound Index
```
db.users.createIndex({ city: 1, age: -1 })
```
Too many indexes = slow inserts & updates.

# 🟣 7. Aggregation Framework (🔥 Interview Favorite)
Example: Total orders per user
```
db.orders.aggregate([
  { $group: { _id: "$userId", total: { $sum: "$amount" } } }
])
```
$lookup (Join)
```
db.orders.aggregate([
  {
    $lookup: {
      from: "users",
      localField: "userId",
      foreignField: "_id",
      as: "userDetails"
    }
  }
])
```
# 🔴 8. Data Modeling
Embedding (Fast read)
```
{
  "orderId": 1,
  "items": [
    { "product": "Laptop", "price": 50000 }
  ]
}
```
Referencing (Reusable data)
```
{
  "orderId": 1,
  "userId": 101
}
```
# 📌 Rule:
- Read heavy → Embed
- Write heavy / reusable → Reference

# 🟤 9. Transactions & ACID
Does MongoDB support ACID?

✅ Yes (from v4.0)

Example Use Case

👉 Bank transfer, order + payment
```
session.startTransaction()
```
⚠️ Slower than single-document operations.

# ⚫ 10. Replication & Sharding
- Replica Set
- Primary
- Secondary
- Automatic failover
- Sharding

Distributes data across servers using shard key
```
sh.shardCollection("db.users", { userId: 1 })
```
# 🟢 11. MongoDB with Node.js (Full Stack)
Connect MongoDB
```
mongoose.connect("mongodb://localhost:27017/app")
```
Schema
```
const userSchema = new mongoose.Schema({
  name: String,
  email: { type: String, required: true }
})
```
Model
```
const User = mongoose.model("User", userSchema)
```
# 🔵 12. Security & Performance
Prevent Injection
```
User.find({ email: req.body.email }) // safe
```
Query Optimization
```
db.users.find({ email: "a@gmail.com" }).explain("executionStats")
```
Backup
```
mongodump
mongorestore
```
# ⭐ 13. Scenario-Based Answers
- When choose MongoDB over SQL?
- Flexible schema
- High traffic
- Real-time apps
- Big data
- Store Images?

👉 Use GridFS or cloud (S3) + URL in MongoDB

Chat App Design
```
{
  "sender": 1,
  "receiver": 2,
  "message": "Hello",
  "timestamp": ISODate()
}
```
