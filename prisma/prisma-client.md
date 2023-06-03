1. Perequisites
   in order to set up Prisma client, you need a Prisma schema file with your database connection, the prisma generatorm and atleast one model:

   ```prisma
   database db {
    url = env("DATABASE_URL")
    provider = "postgresql"
   }

   generator client {
    provider = "prisma-client-js"
   }

   model User {
    id Int @id @default(autorincrement())
    ...
   }
   ```

   also make sure to install the Prisma CLI:
   npm install prisma --save-dev
   npx prisma

2. Installation
   install Prisma Client in your project with the following command:
   -> npm install @ prisma/client
   this command also runs the prisma generate command, which generates Prisma Client into the node_modules/.prisma/client directory.

3. Use Prisma Client to send queries to your database

   ```javascript
   import {Prisma Client} from '@prisma/client'

   const prisma = new PrismaClient()
   ```

   once you have instantiated PrismaClient, you can start sending queries in your code:

   ```javascript
   const newUser = await prisma.user.create({
     data: {
       name: "Alice",
       email: "alice@prisma.io",
     },
   });

   const users = await prisma.user.findMany();
   ```

   All Prisma Client methods return an instance of PrismaPromise which only executes when you call await or .then() or .catch().
