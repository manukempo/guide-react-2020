# React Development | Complete Course

A step-by-step guide of a React course (2020) with the main tips from the Frontend Masters course: https://frontendmasters.com/courses/complete-react-v5/

1. Intro

   - Font:
     - https://github.com/tonsky/FiraCode
     - \$ choco install firacode (as Admin)
     - VSCode: Ctrl + ,
     ```javascript
     "editor.fontFamily": "Fira Code",
     "editor.fontLigatures": true
     ```

2. Pure React
3. Tools:
   - **Prettier** (format project constantly):
     - $ npm i -D prettier
     - Add the script to the package.json:
     ```json
     "scripts": {
         "format": "prettier \"src/**/*.{js,html}\" --write"
     }
     ```
     - $ npm run format
     - Install the Prettier Extension for VSCode:
       - Ctrl+, and look for:
            - format on save
            - require config (check the Prettier: Require Config)
       - Create **.prettierrc** with an empty object (it will apply any config to the files every time you save them)
   - **ESLint**:
     - $ npm i -D eslint eslint-config-prettier
     - Install extra packages for VSCode/ESLint to understand jsx files:
        - $ npm i -D babel-eslint eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-react
     - Install an ESLint plugin to deal with Hooks: 
        - $ npm i -D eslint-plugin-react-hooks
     - Create **.eslintrc.json**
     ```json
     {
        "extends": [
            "eslint:recommended",
            "plugin:import/errors",
            "plugin:react/recommended",
            "plugin:jsx-a11y/recommended", 
            "prettier", 
            "prettier/react"
        ],
        "rules":{
            "react/prop-types": 0,
            "no-console": 1,
            "react-hooks/rules-of-hooks": 2,
            "react-hooks/exhaustive-deps": 1
        },
        "plugins": ["react", "import", "jsx-a11y", "react-hooks"],
        "parserOptions": {
            "ecmaVersion": 2018,
            "sourceType": "module",
            "ecmaFeatures": {
                "jsx": true
            }
        },
        "env": {
            "es6": true,
            "browser": true,
            "node": true
        },
        "settings": {
            "react": {
                "version": "detect"
            }
        }
     } 
     ```
     - Add the script to the package.json:
     ```json
     "lint": "eslint \"src/**/*.{js,jsx}\" --quiet"
     ```
     - $ npm run lint
     - Install the ESLint Extension for VSCode (it will highlight the problems in files)
    - Example of **.gitignore**
    ```
    node_modules/
    .cache/
    dist/
    coverage/
    .vscode/
    .env
    ```
    - **Parcel** (A bundler with no configuration needed -vs Webpack)
        - $ npm i -D parcel-bundler
        - Add the script to the package.json:
        ```json
        "dev": "parcel src/index.html"
        ```
        - This *parcel* can be found on node_modules/.bin/
        - $ npm run dev
            - Go to: http://localhost:1234 
        - It also installs any package dectected from imports. For example:
            - ```javascript
                import { ANIMALS } from '@frontendmasters/pet';
              ```
            - ```json 
                "@frontendmasters/pet": "^1.0.3" 
              ```
    - **React & ReactDOM**
        - $ npm i react react-dom
4. JSX
5. Hooks:
    - Anything started by 'use', such as useState and useEffect;
    - It's a destructuring array where the first one is the default value and the second is an updater function. e.g: [location, setLocation];
    - It should never go inside an if statement;

6. Effects:
    - Related to Lifecycles;
    - useEffect is scheduled during the first render;
    - The last parameter is the list (array) of dependencies (order doesn't matter) that will make render it again. If it's not set, it will render constantly, and if you set it empty [], it will render just once (first time).



