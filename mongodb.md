# MongoDB Full Course (Step-by-Step Guide)

## 1. Introduction to MongoDB
- What is MongoDB?
- Differences between SQL (Relational) and NoSQL (MongoDB)
- Features of MongoDB
- Use cases of MongoDB
- Installation of MongoDB on Windows, macOS, and Linux
- MongoDB Compass (GUI Tool)
- MongoDB Atlas (Cloud Database)

## 2. MongoDB Basics
### 2.1. Understanding NoSQL Structure
- Documents and Collections
- JSON vs BSON
- Schema-less Database Concept

### 2.2. Basic MongoDB Commands
```bash
# Start MongoDB service
mongod

# Start MongoDB shell
mongosh

# Check version
db.version()
```

### 2.3. Databases in MongoDB
```bash
# Show all databases
show dbs

# Create or switch to a database
use database_name

# Check current database
db

# Delete a database
db.dropDatabase()
```

### 2.4. Collections in MongoDB
```bash
# Show all collections
show collections

# Create a collection
db.createCollection("users")

# Drop a collection
db.users.drop()
```

## 3. CRUD Operations in MongoDB
### 3.1. Create (Insert Data)
```bash
# Insert a single document
db.users.insertOne({ name: "John", age: 25, city: "New York" })

# Insert multiple documents
db.users.insertMany([
  { name: "Alice", age: 30, city: "Los Angeles" },
  { name: "Bob", age: 28, city: "Chicago" }
])
```

### 3.2. Read (Query Data)
```bash
# Fetch all documents
db.users.find()

# Fetch with formatting
db.users.find().pretty()

# Fetch with conditions
db.users.find({ age: { $gt: 25 } }) # Users with age greater than 25
```

### 3.3. Update Data
```bash
# Update one document
db.users.updateOne({ name: "John" }, { $set: { age: 26 } })

# Update multiple documents
db.users.updateMany({ city: "New York" }, { $set: { city: "San Francisco" } })
```

### 3.4. Delete Data
```bash
# Delete one document
db.users.deleteOne({ name: "John" })

# Delete multiple documents
db.users.deleteMany({ age: { $lt: 30 } })
```

## 4. MongoDB Query Operators
### 4.1. Comparison Operators
```bash
db.users.find({ age: { $gt: 25 } })  # Greater than
db.users.find({ age: { $lt: 25 } })  # Less than
db.users.find({ age: { $eq: 30 } })  # Equal to
db.users.find({ age: { $ne: 30 } })  # Not equal
```

### 4.2. Logical Operators
```bash
db.users.find({ $or: [{ city: "New York" }, { age: 30 }] })  # OR condition
db.users.find({ $and: [{ age: { $gt: 25 } }, { city: "Chicago" }] })  # AND condition
```

### 4.3. Projection (Selecting Specific Fields)
```bash
db.users.find({}, { name: 1, city: 1, _id: 0 })  # Show only name & city
```

## 5. Indexing in MongoDB
```bash
db.users.createIndex({ name: 1 })  # Ascending order index
db.users.createIndex({ age: -1 })  # Descending order index
db.users.getIndexes()
```

## 6. Aggregation Framework
```bash
db.orders.aggregate([
  { $group: { _id: "$category", totalSales: { $sum: "$price" } } }
])
```

## 7. Relationships in MongoDB
### 7.1. One-to-One Relationship
```bash
db.users.insertOne({ name: "John", contact: { email: "john@example.com", phone: "1234567890" } })
```

### 7.2. One-to-Many Relationship
```bash
db.orders.insertOne({ userId: ObjectId("someUserId"), items: [{ product: "Laptop", quantity: 1 }] })
```

## 8. Transactions in MongoDB
```bash
const session = db.getMongo().startSession();
session.startTransaction();
try {
  session.getDatabase("shop").orders.insertOne({ orderId: 123, amount: 500 }, { session });
  session.commitTransaction();
} catch (e) {
  session.abortTransaction();
}
session.endSession();
```

## 9. Security & Authentication
```bash
db.createUser({
  user: "admin",
  pwd: "password",
  roles: [{ role: "readWrite", db: "shop" }]
})
```

## 10. MongoDB Backup & Restore
```bash
# Backup
mongodump --db database_name --out /backup/path

# Restore
mongorestore --db database_name /backup/path/database_name
```

## 11. MongoDB with Node.js
```javascript
const { MongoClient } = require('mongodb');
const uri = "mongodb://localhost:27017";
const client = new MongoClient(uri);

async function connectDB() {
  await client.connect();
  console.log("Connected to MongoDB");
}

connectDB();
```

## 12. Real-World Projects
1. User Management System
2. E-commerce Database
3. Blog CMS with MongoDB
4. Realtime Chat App (with WebSockets)
5. Inventory Management System

