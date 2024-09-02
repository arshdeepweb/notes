# MongoDB Command Cheat Sheet

This document provides a quick reference guide for commonly used MongoDB commands, along with their syntax and examples.

## Table of Contents

1. [Terminology](#terminology)
2. [Basic Commands](#basic-commands)
3. [Create Operations](#create-operations)
4. [Read Operations](#read-operations)
5. [Update Operations](#update-operations)
6. [Delete Operations](#delete-operations)
7. [Complex Filters](#complex-filters)
8. [Complex Updates](#complex-updates)
9. [Read Modifiers](#read-modifiers)

---

## Terminology

### Database

- **Description:** A container for collections, similar to an SQL database.
- **Definition:** A container for collections, similar to an SQL database. Each project typically has its own database with various collections.

### Collection

- **Description:** A grouping of documents inside a database, analogous to a table in SQL.
- **Definition:** Each data type (users, posts, products) generally has its own collection.

### Document

- **Description:** A record within a collection, equivalent to a row in SQL.
- **Definition:** Typically, one document represents one object in the collection, and it is a JSON object.

### Field

- **Description:** A key-value pair within a document, similar to a column in SQL.
- **Definition:** Fields in MongoDB can store JSON objects, arrays, and other complex data types.

## Basic Commands

### mongosh

- **Description:** Open a connection to your local MongoDB instance.
- **Syntax:** `mongosh`

### show dbs

- **Description:** Show all databases in the current MongoDB instance.
- **Syntax:** `show dbs`

### use <dbname>

- **Description:** Switch to the database provided by dbname.
- **Syntax:** `use myDatabase`

### db

- **Description:** Show the current database name.
- **Syntax:** `db`

### cls

- **Description:** Clear the terminal screen.
- **Syntax:** `cls`

### show collections

- **Description:** Show all collections in the current database.
- **Syntax:** `show collections`

### db.dropDatabase()

- **Description:** Delete the current database.
- **Syntax:** `db.dropDatabase()`

### exit

- **Description:** Exit the mongosh session.
- **Syntax:** `exit`

## Create Operations

### insertOne

- **Description:** Create a new document inside the specified collection.
- **Syntax:** `db.users.insertOne({ name: "Kyle" })`
- **Example:** Add a new document with the name of Kyle into the users collection.

### insertMany

- **Description:** Create multiple new documents inside a specific collection.
- **Syntax:** `db.users.insertMany([{ age: 26 }, { age: 20 }])`
- **Example:** Add two new documents with the age of 26 and 20 into the users collection.

## Read Operations

### find

- **Description:** Get all documents.
- **Syntax:** `db.users.find()`
- **Example:** Get all users.

### find (with filter)

- **Description:** Find all documents that match the filter object.
- **Syntax:** `db.users.find({ name: "Kyle" })`
- **Example:** Get all users with the name Kyle.

### findOne

- **Description:** The same as find, but only return the first document that matches the filter object.
- **Syntax:** `db.users.findOne({ name: "Kyle" })`
- **Example:** Get the first user with the name Kyle.

### countDocuments

- **Description:** Return the count of the documents that match the filter object.
- **Syntax:** `db.users.countDocuments({ name: "Kyle" })`
- **Example:** Get the number of users with the name Kyle.

## Update Operations

### updateOne

- **Description:** Update the first document that matches the filter object with the data passed into the update object.
- **Syntax:** `db.users.updateOne({ age: 20 }, { $set: { age: 21 } })`
- **Example:** Update the first user with an age of 20 to the age of 21.

### updateMany

- **Description:** Update all documents that match the filter object with the data passed into the update object.
- **Syntax:** `db.users.updateMany({ age: 12 }, { $inc: { age: 3 } })`
- **Example:** Update all users with an age of 12 by adding 3 to their age.

### replaceOne

- **Description:** Replace the first document that matches the filter object with the exact object passed as the second parameter.
- **Syntax:** `db.users.replaceOne({ age: 12 }, { age: 13 })`
- **Example:** Replace the first user with an age of 12 with an object that has the age of 13 as its only field.

## Delete Operations

### deleteOne

- **Description:** Delete the first document that matches the filter object.
- **Syntax:** `db.users.deleteOne({ age: 20 })`
- **Example:** Delete the first user with an age of 20.

### deleteMany

- **Description:** Delete all documents that match the filter object.
- **Syntax:** `db.users.deleteMany({ age: 12 })`
- **Example:** Delete all users with an age of 12.

## Complex Filters

### $eq

- **Description:** Check for equality.
- **Syntax:** `db.users.find({ name: { $eq: "Kyle" } })`
- **Example:** Get all users with the name Kyle.

### $ne

- **Description:** Check for not equal.
- **Syntax:** `db.users.find({ name: { $ne: "Kyle" } })`
- **Example:** Get all users with a name other than Kyle.

### $gt / $gte

- **Description:** Check for greater than and greater than or equal to.
- **Syntax:** `db.users.find({ age: { $gt: 12 } })`
- **Example:** Get all users with an age greater than 12.

### $lt / $lte

- **Description:** Check for less than and less than or equal to.
- **Syntax:** `db.users.find({ age: { $lt: 12 } })`
- **Example:** Get all users with an age less than 12.

### $in

- **Description:** Check if a value is one of many values.
- **Syntax:** `db.users.find({ name: { $in: ["Kyle", "Mike"] } })`
- **Example:** Get all users with a name of Kyle or Mike.

### $nin

- **Description:** Check if a value is none of many values.
- **Syntax:** `db.users.find({ name: { $nin: ["Kyle", "Mike"] } })`
- **Example:** Get all users that do not have the name Kyle or Mike.

### $and

- **Description:** Check that multiple conditions are all true.
- **Syntax:** `db.users.find({ $and: [{ age: 12 }, { name: "Kyle" }] })`
- **Example:** Get all users that have an age of 12 and the name Kyle.

### $or

- **Description:** Check that one of multiple conditions is true.
- **Syntax:** `db.users.find({ $or: [{ age: 12 }, { name: "Kyle" }] })`
- **Example:** Get all users with a name of Kyle or an age of 12.

### $not

- **Description:** Negate the filter inside of $not.
- **Syntax:** `db.users.find({ name: { $not: { $eq: "Kyle" } } })`
- **Example:** Get all users with a name other than Kyle.

### $exists

- **Description:** Check if a field exists.
- **Syntax:** `db.users.find({ name: { $exists: true } })`
- **Example:** Get all users that have a name field.

### $expr

- **Description:** Do comparisons between different fields.
- **Syntax:** `db.users.find({ $expr: { $gt: ["$balance", "$debt"] } })`
- **Example:** Get all users that have a balance that is greater than their debt.

## Complex Updates

### $set

- **Description:** Update only the fields passed to $set.
- **Syntax:** `db.users.updateOne({ age: 12 }, { $set: { name: "Hi" } })`
- **Example:** Update the name of the first user with the age of 12 to the value Hi.

### $inc

- **Description:** Increment the value of the field by the amount given.
- **Syntax:** `db.users.updateOne({ age: 12 }, { $inc: { age: 2 } })`
- **Example:** Add 2 to the age of the first user with the age of 12.

### $rename

- **Description:** Rename a field.
- **Syntax:** `db.users.updateMany({}, { $rename: { age: "years" } })`
- **Example:** Rename the field age to years for all users.

### $unset

- **Description:** Remove a field.
- **Syntax:** `db.users.updateOne({ age: 12 }, { $unset: { age: "" } })`
- **Example:** Remove the age field from the first user with an age of 12.

### $push

- **Description:** Add a value to an array field.
- **Syntax:** `db.users.updateMany({}, { $push: { friends: "John" } })`
- **Example:** Add John to the friends array for all users.

### $pull

- **Description:** Remove a value from an array field.
- **Syntax:** `db.users.updateMany({}, { $pull: { friends: "Mike" } })`
- **Example:** Remove Mike from the friends array for all users.

## Read Modifiers

### sort

- **Description:** Sort the results of a find by the given fields.
- **Syntax:** `db.users.find().sort({ name: 1, age: -1 })`
- **Example:** Get all users sorted by name in alphabetical order and then if any names are the same sort by age in reverse order.

### limit

- **Description:** Only return a set number of documents.
- **Syntax:** `db.users.find().limit(2)`
- **Example:** Only return the first 2 users.

### skip

- **Description:** Skip a set number of documents from the beginning.
- **Syntax:** `db.users.find().skip(4)`
- **Example:** Skip the first 4 users when returning results. This is great for pagination when combined with limit.

---

This cheat sheet should provide you with a handy reference for many commonly used MongoDB commands. Feel free to add more commands as you learn them!
