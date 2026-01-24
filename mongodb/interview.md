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


# 🟢 BASICS (1–10)

1. What is MongoDB?
→ MongoDB is a NoSQL, document-oriented database.
****
2. SQL or NoSQL?
→ NoSQL
****
3. What is a document?
→ JSON-like record
```
{ "name":"Sonam", "age":22 }
```
4. What is a collection?
→ Group of documents (like table)
****
5. MongoDB vs MySQL?
→ Schema-less vs fixed schema
****
6. What is BSON?
→ Binary JSON (faster + more data types)
****
7. Why schema-less?
→ Flexible structure, easy scaling
****
8. What is _id?
→ Unique primary key
****
9. MongoDB data types?
→ String, Number, Array, ObjectId, Date
****
10. How data stored internally?
→ BSON format
****
# 🟡 CRUD (11–20)

11. Insert data?
```
    db.users.insertOne({name:"A"})
```
12. insertOne vs insertMany?
→ Single vs multiple docs
****
13. Read data?
```
db.users.find()
```
14. findOne()?
→ Returns first match

15. Update document?
```
db.users.updateOne({name:"A"},{$set:{age:23}})
```
16. updateOne vs updateMany?
→ One vs multiple docs
****
17. $set?
→ Updates specific field
****
18. Delete document?
```
db.users.deleteOne({name:"A"})
```
19. deleteOne vs deleteMany?
→ One vs many
****
20. If update condition fails?
→ No change (unless upsert)

# 🟠 QUERY & OPERATORS (21–30)

21. Comparison operators?
→ $gt,$lt,$gte,$lte,$eq
****
22. Logical operators?
→ $and,$or,$not
****
23. $and vs $or?
→ All true vs any true
****
24. $in / $nin?
→ Match inside / outside list
****
25. $exists?
→ Field exists or not
26. $regex?
```
{name:{$regex:"^S"}}
```
27. Sort?
```
.find().sort({age:-1})
```
28. Limit & skip?
```
.limit(5).skip(10)
```
29. Projection?
→ Select fields

30. Fetch selected fields?
```
.find({}, {name:1})
```
# 🔵 INDEXING (31–40)

31. What is index?
→ Improves search speed

32. Why indexing?
→ Faster queries

33. Index types?
→ Single, Compound, Text, Hashed

34. Compound index?
```
{city:1, age:-1}
```
35. Text index?
→ Text search

36. Hashed index?
→ Sharding support

37. Index cardinality?
→ Unique values count

38. Can index slow DB?
→ Yes (write operations)

39. Create / drop index?
```
createIndex(), dropIndex()
```
40. Check performance?
```
.explain()
```
# 🟣 AGGREGATION (41–50)

41. Aggregation?
→ Data processing pipeline

42. find vs aggregate?
→ Simple vs complex

43. Pipeline?
→ Series of stages

44. $match?
→ Filter

45. $group?
```
{$group:{_id:"$user",sum:{$sum:"$amt"}}}
```
46. $sum vs $count?
→ Add values vs count docs

47. $project?
→ Reshape output

48. $lookup?
→ Join collections

49. MongoDB join vs SQL join?
→ $lookup vs JOIN

50. Use case?
→ Reports, analytics
🔴 DATA MODELING (51–60)

51. Relationships?
→ Embed or reference

52. Embedding vs referencing?
→ Fast read vs reusable

53. When embed?
→ One-to-few

54. When reference?
→ One-to-many

55. One-to-One?
→ User ↔ Profile

56. One-to-Many?
→ User → Orders

57. Many-to-Many?
→ Students ↔ Courses

58. Best practices?
→ Avoid deep nesting

59. Avoid duplication?
→ Referencing

60. Large datasets?
→ Sharding

# 🟤 TRANSACTIONS (61–66)

61. Transactions supported?
→ Yes (v4+)

62. ACID?
→ Atomic, Consistent, Isolated, Durable

63. Single vs multi doc?
→ Faster vs safe

64. Atomicity?
→ Single document atomic

65. Use cases?
→ Payments, banking

66. Limitations?
→ Slower, complex

# ⚫ REPLICATION & SHARDING (67–75)

67. Replication?
→ Data copies

68. Replica set?
→ Primary + secondary

69. Primary vs secondary?
→ Write vs read

70. Failover?
→ Auto primary switch

71. Sharding?
→ Data distribution

72. Why sharding?
→ Scale horizontally

73. Shard key?
→ Partition key

74. Chunk?
→ Data block

75. Replication vs sharding?
→ Availability vs scalability

# 🟢 BACKEND INTEGRATION (76–85)

76. Connect Node.js?
```
mongoose.connect(url)
```
77. Mongoose?
→ ODM library

78. Driver vs Mongoose?
→ Low-level vs schema-based

79. Schema?
→ Structure definition

80. Model?
→ Schema instance

81. Population?
→ Reference resolving

82. Middleware?
→ Pre/Post hooks

83. Validation?
→ Required, min, max

84. Error handling?
→ try/catch

85. Prevent injection?
→ Validate inputs
# 🔵 PERFORMANCE & SECURITY (86–95)

86. Optimize queries?
→ Indexing

87. explain()?
→ Query stats

88. Large collections?
→ Pagination

89. Secure MongoDB?
→ Auth + roles

90. Auth methods?
→ SCRAM, x.509

91. RBAC?
→ Role-based access

92. Backup & restore?
→ mongodump

93. Scale MongoDB?
→ Sharding

94. Monitor?
→ Atlas, logs

95. Common issues?
→ Missing indexes

# ⭐ SCENARIO BASED (96–100)

96. Choose MongoDB over SQL?
→ Flexible schema, big data

97. E-commerce schema?
→ Users, Orders, Products

98. Handle high traffic?
→ Index + sharding

99. File uploads?
→ GridFS / cloud URL

100. Chat app design?
```
{ sender, receiver, message, time }
```
