# Lab React

### Steps to add pre-commit hook to React project

> [Husky](https://github.com/typicode/husky) improves your commits and more [🐶 woof!](https://typicode.github.io/husky/)
> _You can use it to lint your commit messages, run tests, lint code, etc... when you commit or push. Husky supports all Git hooks._

Follow this instruction:
1. Open your React project;
2. Install husky:
    - ``npm install husky --save-dev``
3. Enable Git hooks
    - ``npx husky install``
    - _After this step you should have .husky folder in the root of your project_
4. Add new scripts to your package.json:
    - ```
        {
         "scripts": {
           // ...
           "test:nowatch": "react-scripts test --watchAll=false",
           "prepare": "husky install",
           "prepublish": "npm run eslint:fix"
         }
        }
      ```
5. Run (to add a command to a hook):
    - ``npx husky add .husky/pre-commit "npm run prepublish"``









