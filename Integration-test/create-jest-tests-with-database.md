# 
## 1 -  Install the dependencies

 ```
 npm i dotenv
 ```
 
 ```
 npm i -D dotenv-cli
 ```


## 2 - Create the .env.test file and configure it by changing the database name to [database]_test
 
 ```
DATABASE_URL="postgres://[USER]:[PASSWORD]@localhost:5432/[database_name]_test?schema=public
 ```

## 3- Inside the src folder, create the 'config' folder, and after that, create the envs.ts file with:
 
 ```
 import dotenv from "dotenv";
 
 export function loadEnvs(){
    let path = ".env";
    if(process.env.NODE_ENV === "test"){
        path = "env.test";
    }
    
    dotenv.config({ path})
 }
 
 ```
 
 ## 4 - Run in the terminal, creating the tests database
 
 ```
npx dotenv -e .env.test npx prisma migrate dev --name jobs postgress-init
 ```
  ## 5 - Run application
 
 ```
npx nodemon src/app.ts
 ```
 
 ## 6 - Run application test
 
 ```
npx dotenv -e .env.test npx jest
 ```

# ____________________________________________________________________________________



## X- Import database and clear the database before running any test
 
 ```
 import prisma from "../src/database/database"
 
 beforeAll(async () => {
    await prisma.jobs.deleteMany({})
 })
 ```

## X- Create afterAll and delete everything when the test is finished
 
 ```
  afterAll(async () => {
    await prisma.jobs.deleteMany({})
  })
 
 ```
 
 Also exists:
- beforeEach --> runs before each test.
- afterEach --> run after each test

# ____________________________________________________________________________________

 
 ## 3- Write test scenarios
 
 ```
 describe(´Testando Math Helper´, () => {
 
      it(´Testando a função sum´, () => {
         ~~~ add the expected input and output
      })
 
 })
 ```
