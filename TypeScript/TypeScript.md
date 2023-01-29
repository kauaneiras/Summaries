## Intalação e Uso

- Como é uma ferramenta para o desenvolvedor, o Typescript deve ser instalado nas "dev dependencies". Assim, para instalá-lo usamos:

``` npm i -D typescript ```
- Para usar o typescript com o Express precisamos instalar os tipos prontos do express:
``` npm i -D @types/express ```
- Para converter um código para typescript: 
``` coloca a extesão .ts no arquivo ```
- Importa os tipos TS do express:
``` import {Request, Response} form 'express' ```
- Usa os tipos no código colocando dois pontos (:) + o tipo:
``` 
function calculate (req: Request, res: Response) {
   
   const {salary} = req.query
   
   \\ agora eu consigo ver que "salary" é uma string

   const newSalary = salary + (salary * 0.3)

   \\ usando typescript ele vai sinalizar o erro na linha acima, já que não é possivel fazer a operação com strings. Assim, fica mais claro que eu preciso convertê-las para number. 
}
```
