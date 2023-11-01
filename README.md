# ts-mod-4-react

TS - React

= Creating a new project
$ npx create-react-app my-app --template typescript

= Project migration to TypeScript
-Install TypeScript and React types:
$ npm install --save typescript @types/react @types/react-dom

-Add the TypeScript configuration:
In the root directory of the project, create a file tsconfig.json

{
  "compilerOptions": {
    "target": "es5",
    "lib": ["dom", "dom.iterable", "esnext"],
    "allowJs": true,
    "skipLibCheck": true,
    "esModuleInterop": true,
    "allowSyntheticDefaultImports": true,
    "strict": true,
    "forceConsistentCasingInFileNames": true,
    "noFallthroughCasesInSwitch": true,
    "module": "esnext",
    "moduleResolution": "node",
    "resolveJsonModule": true,
    "isolatedModules": true,
    "noEmit": true,
    "jsx": "react-jsx"
  },
  "include": ["src", "@types"]
}

-Describe types for non-JS files:
Create a folder @types in the root directory of the project and add the custom.d.ts file. Inside this file, write the following code:

declare module "*.svg" {
  const content: any;
  export default content;
}

declare module "*.png" {
  const content: any;
  export default content;
}
This is necessary for TypeScript to correctly handle files with .svg and .png extensions. Without it, imports of the type import logo from "./logo.svg"; will cause an error.

- Rename the files:
TypeScript files have the extension .ts for non-JSX files and .tsx for JSX files. You need to rename all .js and .jsx files to .ts and .tsx respectively.
You can do this incrementally because you have specified "allowJs": true in the TypeScript configuration, which allows the project to mix TypeScript and JavaScript files.

= Структура файлів та папок

my-app/

├── src/
│ ├── components/
│ │ ├── App/
│ │ │ ├── App.tsx
│ │ │ ├── index.ts
│ │ │ └── App.types.ts

Inside the App folder are:

1. App.tsx is the main component file.
2. index.ts — the file that exports the App component. This is done for more convenient import in other files. Instead of import App from '../components/App/App', we can write import App from '../components/App'.
In working with TypeScript, we often come across a situation where types declared for one component are also needed elsewhere in the project. In this case, a good practice would be to separate these types into a separate file.
3. App.types.ts is a file that contains the types used in the App component. With a large number of types or their reuse in other parts of the application, this approach makes the code easier to maintain and more readable.

==========================================================================
mii@DESKTOP-O1VK09I MINGW64 /c/WORK/GoIT/TypeScript/GitHub/ts-mod-4-react (main)
$ npx create-react-app my-app --template typescript

Creating a new React app in C:\WORK\GoIT\TypeScript\GitHub\ts-mod-4-react\my-app.

Installing packages. This might take a couple of minutes.
Installing react, react-dom, and react-scripts with cra-template-typescript...


added 1463 packages in 48s

242 packages are looking for funding
  run `npm fund` for details        

Installing template dependencies using npm...

added 47 packages, removed 1 package, and changed 2 packages in 6s

246 packages are looking for funding
  run `npm fund` for details

We detected TypeScript in your project (src\App.test.tsx) and created a tsconfig.json file for you.

Your tsconfig.json has been populated with default values.

Removing template package using npm...


removed 1 package, and audited 1509 packages in 3s

246 packages are looking for funding
  run `npm fund` for details

8 vulnerabilities (2 moderate, 6 high)

To address all issues (including breaking changes), run:
  npm audit fix --force

Run `npm audit` for details.

Success! Created my-app at C:\WORK\GoIT\TypeScript\GitHub\ts-mod-4-react\my-app
Inside that directory, you can run several commands:

  npm start
    Starts the development server.

  npm run build
    Bundles the app into static files for production.

  npm test
    Starts the test runner.

  npm run eject
    Removes this tool and copies build dependencies, configuration files
    and scripts into the app directory. If you do this, you can’t go back!

We suggest that you begin by typing:

  cd my-app
  npm start

Happy hacking!

mii@DESKTOP-O1VK09I MINGW64 /c/WORK/GoIT/TypeScript/GitHub/ts-mod-4-react (main)
$

$ cd my-app

mii@DESKTOP-O1VK09I MINGW64 /c/WORK/GoIT/TypeScript/GitHub/ts-mod-4-react/my-app (main)
$npm
