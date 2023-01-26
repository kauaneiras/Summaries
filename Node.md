## Installation and Use Of the Node.js

- How to start a project in Node:
``` npm init -y ```
- Para usar o typescript com o Express precisamos instalar os tipos prontos do express:
``` npm i -D @types/express ```
- Para converter um código para typescript: 
``` coloca a extesão .ts no arquivo ```
- Importa os tipos TS do express:
``` import {Request, Response} form 'express' ```
- Usa os tipos no código colocando dois pontos (:) + o tipo:
``` 
import dotenv from "dotenv";
import carsRouter from "./routes/carsRouter.js";
import handleErrorsMiddleware from "./middlewares/errorHandlerMiddleware.js";
dotenv.config();

const app = express();
app.use(json());
app.use(carsRouter);
app.use(handleErrorsMiddleware);

const port = +process.env.PORT || 5000;
app.listen(port, () => {
  console.log(`Server is up and running on port: ${port}`);
})
```
