## Installation and Use of Prisma if you have an existing database
To install the prism in your project, use the command:

``` npm i prisma ```

*You need to have a database formed with some spreadsheets filled with data*

1 - Inside the terminal that contains your project, use the command:

``` npx prisma init ```

*A folder "prisma" with "schema.prisma" will be created and instructions on how to configure your prism will appear in the terminal.*

2 - Follow Prisma setup instructions within your project: 
``` 
Next steps:
1. Set the DATABASE_URL in the .env file to point to your existing database. If your database has no tables yet, read https://pris.ly/d/getting-started
2. Set the provider of the datasource block in schema.prisma to match your database: postgresql, mysql, sqlite, sqlserver, mongodb or cockroachdb.
3. Run npx prisma db pull to turn your database schema into a Prisma schema.
4. Run npx prisma generate to generate the Prisma Client. You can then start querying your database.
```
3 - Example of configuring .env with a postgress database:
```
PORT=4000
DATABASE_URL='postgres://[USER]:[PASSWORD]@localhost:5432/[DATABASENAME]?schema=public'
```

4 - check that the "schema.prisma" file is configured with the correct database information.

5 - Then pull from the database with Prisma. For this, use the command:

``` npx prisma db pull ```

6 - Now generate the Prisma client in your application:

``` npx prisma generate ```

*Prisma will return instructions on how to import it into your project.*

```
import { PrismaClient } from '@prisma/client'
const prisma = new PrismaClient()
```

7 - Install Prisma as a developer dependency

```
npm i -D @prisma/client
```

8 - Configure your database file with:

```
import pkg from '@prisma/client';

const { PrismaClient } = pkg;
const prisma = new PrismaClient();

export default prisma;
```

**Prisma is already configured in your project. Now just import it into each file and use it when needed**
