
# Simple Function Test

## 1- Import file that will be tested
 
 ```
 import { sum } from "../src/helpers/math-helper"
 ```

## 2- Insert a describe
 
 ```
 describe(´Testando Math Helper´, () => {
 
  ~~~ add test scenarios here
 
 })
 ```
 
 ## 3- Write test scenarios
 
 ```
 describe(´Testando Math Helper´, () => {
 
      it(´Testando a função sum´, () => {
         ~~~ add the expected input and output
      })
 
 })
 ```
 
  ## 4- Write test scenarios
 
 ```
 describe(´Testando Math Helper´, () => {
 
      it(´Testando a função sum´, () => {
          const result = sum (1, 2); 
          
          expect(result).toBe(3); --> it is expected that 1 + 2 = 3
      })
 
 })
 ```
 
# Test a databaseless API
  
## 1- Install 'supertest' lib
 
 ```
 npm - -D supertest @types/supertest
 ```

  
## 2- Export the app|server const being listened to from the main program.
 
 ```
 export default app|server;
 ```
 
   
## 3- Import App file in file test and import supertest
 
 ```
 import server from "../src/app";
 import supertest from "supertest";
 ```
 
 ## 4- Call super test passing the server as a parameter
 
 ```
const api = supertest(server);
 ```
 
 ## 5- Create the tests with Jest
  
 ```
describe(´Testing  a API´, async () => {
  it('Testando GET: /jobs', () => {
    
    // makes request on route 'jobs'
    const result = await api.get('/jobs');
    
    // put expected result
    expect(result.status).toBe(200);
    //equal
    expect(result.body).toEqual([1, 2, 3]);
    //contain
    expect(result.body.toContain(2); 
    //array
    expect(result.body).toEqual(expect.arrayContaining([3, 10])); 
    //object equal
    expect(result.body).toMatchObject({
      "title": "LALALA",
      "salary": 3000,
      "until": "2021-01-01T00:00:000Z",
     })
     //object without data
     expect(result.body).ToEqual({
         id: expect.any(Number),
         title: expect.any(String),
         salary: expect.any(Number)
     })
     
     //array of object
     expect(result.body).ToEqual({
        expect.arrayContaining([
            expect.objectContaining(
                {
                  id: expect.any(Number),
                  title: expect.any(String),
                  salary: expect.any(Number
                }
            )
        ])
     })
  })
})
 ```
