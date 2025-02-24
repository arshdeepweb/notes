# Prisma Step-by-Step Guide

## 1. Introduction to Prisma
### What is Prisma?
- Prisma is a modern database ORM (Object-Relational Mapping) for Node.js & TypeScript.
- It simplifies database access, supports migrations, and works well with PostgreSQL, MySQL, SQLite, and more.

### Installation
```sh
npm install @prisma/client
npm install --save-dev prisma
```

### Initializing Prisma in a Project
```sh
npx prisma init
```
- This creates a `prisma` folder with `schema.prisma` file.

---

## 2. Configuring the Database Connection
### Updating `schema.prisma`
Modify `datasource` to match your database:
```prisma
datasource db {
  provider = "mysql"  # Change to "postgresql" or "sqlite" if needed
  url      = env("DATABASE_URL")
}
```

### Setting up Environment Variables
Add database connection URL to `.env`:
```env
DATABASE_URL="mysql://user:password@localhost:3306/mydb"
```

---

## 3. Defining Models in Prisma
### Example Model in `schema.prisma`
```prisma
model User {
  id        Int     @id @default(autoincrement())
  name      String
  email     String  @unique
  posts     Post[]
}

model Post {
  id        Int     @id @default(autoincrement())
  title     String
  content   String?
  author    User    @relation(fields: [authorId], references: [id])
  authorId  Int
}
```

---

## 4. Running Migrations
### Generating and Applying Migrations
```sh
npx prisma migrate dev --name init
```
- This creates a `migrations/` folder and applies schema changes to the database.

### Viewing the Database
```sh
npx prisma studio
```
- Opens a web-based database viewer.

---

## 5. Generating the Prisma Client
```sh
npx prisma generate
```
- This creates a generated client for querying the database.

---

## 6. Using Prisma Client in Code
### Importing and Initializing Prisma Client
```ts
import { PrismaClient } from '@prisma/client';
const prisma = new PrismaClient();
```

### Creating a User
```ts
const user = await prisma.user.create({
  data: {
    name: "John Doe",
    email: "john@example.com"
  }
});
```

### Fetching All Users
```ts
const users = await prisma.user.findMany();
```

### Fetching a User by ID
```ts
const user = await prisma.user.findUnique({ where: { id: 1 } });
```

### Updating a User
```ts
const updatedUser = await prisma.user.update({
  where: { id: 1 },
  data: { name: "Jane Doe" }
});
```

### Deleting a User
```ts
await prisma.user.delete({ where: { id: 1 } });
```

---

## 7. Relations and Queries
### Fetching Related Data (Include)
```ts
const userWithPosts = await prisma.user.findUnique({
  where: { id: 1 },
  include: { posts: true }
});
```

### Fetching Related Data (Select)
```ts
const userName = await prisma.user.findUnique({
  where: { id: 1 },
  select: { name: true }
});
```

---

## 8. Advanced Queries
### Filtering and Pagination
```ts
const paginatedUsers = await prisma.user.findMany({
  take: 10,
  skip: 5,
  orderBy: { name: 'asc' }
});
```

### Aggregations
```ts
const userCount = await prisma.user.count();
```

### Transactions
```ts
await prisma.$transaction([
  prisma.user.create({ data: { name: "Alice", email: "alice@example.com" } }),
  prisma.post.create({ data: { title: "First Post", authorId: 1 } })
]);
```

---

## 9. Seeding the Database
### Creating a Seed Script
Add this to `prisma/seed.ts`:
```ts
import { PrismaClient } from '@prisma/client';
const prisma = new PrismaClient();

async function main() {
  await prisma.user.create({ data: { name: "Admin", email: "admin@example.com" } });
}

main().catch(e => console.error(e)).finally(async () => await prisma.$disconnect());
```

### Running the Seed Script
```sh
npx prisma db seed
```

---

## 10. Deploying Prisma
### Applying Migrations in Production
```sh
npx prisma migrate deploy
```

### Generating Prisma Client in Production
```sh
npx prisma generate
```

---

## Conclusion
This guide covers Prisma setup, schema modeling, queries, and advanced database management. Continue exploring Prisma's features for more efficient database handling!

