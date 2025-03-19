# [ExpressJS](https://expressjs.com/) with [TypeScript](https://www.typescriptlang.org/)

## 1. Initialize Project

Create a new directory and initialize the project with `yarn` :

```bash
mkdir project-name
cd project-name
yarn init -y
```

## 2. Install Dependencies

Install necessary dependencies:

```bash
yarn add express
yarn add -D typescript @types/express @types/node ts-node nodemon
```

* `typescript`: TypeScript compiler
* `@types/node`: Type definitions for Node.js
* `@types/express`: Type definitions for Express
* `ts-node`: Run TypeScript files without compiling
* `nodemon`: Run File Without Restarting

## 3. Initialize TypeScript Configuration

Run the following command to generate the `tsconfig.json` file:

```bash
npx tsc --init
```

Then, modify the generated `tsconfig.json` to look like this:

```json
{
  "compilerOptions": {
    "target": "es2016",
    "module": "commonjs",
    "rootDir": "./src",
    "outDir": "./dist",
    "esModuleInterop": true,
    "forceConsistentCasingInFileNames": true,
    "strict": true,
    "skipLibCheck": true
  }
}
```

## 4. Add Build and Start Scripts (package.json)

Update the `package.json` to add build and start scripts:

```json
{
  "scripts": {
    "start": "node dist/index.js",
    "dev": "nodemon src/index.ts",
    "build": "tsc"
  }
}
```

* `start`: Runs the compiled JavaScript code.
* `dev`: Runs the TypeScript code directly (for development).
* `build`: Compiles TypeScript to JavaScript.

## 5. Running the Project

You can now run the project with the following commands:

* For development (without compilation):  
  

```bash
  yarn run dev
  ```

* For production (after compiling):  
  

```bash
  yarn run build
  yarn start
  ```
