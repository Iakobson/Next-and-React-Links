# Lab React

### Steps to add pre-commit hook to React project

> [Husky](https://github.com/typicode/husky) improves your commits and more [🐶 woof!](https://typicode.github.io/husky/)
> _You can use it to lint your commit messages, run tests, lint code, etc... when you commit or push. Husky supports all Git hooks._

**Follow this instruction:**
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

**Result:**\
Every time you want to add changes to the repository, ``eslint:fix`` and ``test:nowatch`` commands will be run.\
If command fails, your commit will be automatically aborted.\
You will not be able to commit changes until you fix the error(s).

### Steps to add EsLint and Prettier to React project:
* Step 1. For VSCode and WebStorm
  + Open your react project
  + Install Eslint as development dependence
    - ``npm i eslint --save-dev``
  + Initiate Eslint in your project:
    - ``eslint --init``
    - _Answer the questions_
    - _ESLINT_instruction.md_
  + Now you have eslintrc.json file.
    - _It may take a while for the eslintrc.json file to appear in the project folder_
    - _Replace the code in the eslintrc.json file_
  + Run
    - ``npm i -D eslint-config-prettier eslint-plugin-prettier prettier``
* Step 2. If you use VSCode:
  + Install EsLint plugin
  + Change your VScode settings
    - _To open user setting config press F1, enter 'settings' and choose 'Open User Settings'_
    - _Enter 'eslint' in the search panel._
* Step 3. For VSCode and WebStorm
  + Add script to package.json file
    - ```
        "eslint": "eslint --ext .js --ext .jsx src",
        "eslint:fix": "eslint --fix --ext .js --ext .jsx src"
      ```

**Result:**
  - _Every place in your code with code style problem should be highlighted_
  - _Hover on the problem and see what went wrong_
  - _You can fix separate problem by clicking ESLint:_ `Fix 'prettier/prettier`







