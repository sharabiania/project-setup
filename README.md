# project-setup
## typescript
This is to install typescript locally (not globally):
- npm i
- npm i typscript --save-dev
- npm i tslint --save-dev
- int the package.json, under "scripts" add: `"tsc":"tsc"`
- npm run tsc -- -v (to check the version)
- npm run tsc -- --init (to generate the ts.config file)
- in the tsconfig file set `outDir: "dist"`
- in the package.json under scripts add: `"tslint": "tslint"`
- npm run tslint -- --init (to initialize the tslint)
- in the package.json under scripts add: `"start": "tsc && node dist/server.js"`
- in the package.json set `"main": "dist/server.js"
This initial package.json should look something like this:

```
{
  "name": "typscript-sandbox",
  "version": "1.0.0",
  "description": "",
  "main": "dist/server.js",
  "scripts": {
    "tsc": "tsc",
    "tslint": "tslint",
    "start": "tsc && node dist/server.js"
  },
  "author": "Ali Sharabiani",
  "license": "ISC",
  "devDependencies": {   
    "tslint": "^6.1.3",
    "typescript": "^4.4.2"
  }
}
```

## setup express with typescript:
- npm i express
- npm i @types/express
- add server.ts file:
```
import express from 'express';

const app = express();
const port = 3000;

app.get('/', (req, res) => {
  res.send("hello world");
});

app.listen(port, () => {  
  return console.log(`server is listening on ${port}`);
});
```
