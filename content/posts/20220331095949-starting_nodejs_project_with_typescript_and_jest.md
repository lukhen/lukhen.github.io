+++
title = "starting nodejs project with typescript and jest"
publishDate = 2022-03-31
categories = ["zettel"]
draft = false
+++

mkdir projectname
cd ./projectname

npm init
npm install typescript @types/node ts-node jest @types/jest ts-jest eslint @typescript-eslint/parser @typescript-eslint/eslint-plugin --save-dev
tsc --init

//linting xxx
touch .eslintrc.js
// enter the following
****\*****
module.exports = {
  parser: "@typescript-eslint/parser",
  parserOptions: {
    ecmaVersion: "latest", _/ Allows the use of modern ECMAScript features
    sourceType: "module", /_ Allows for the use of imports
  },
  extends: ["plugin:@typescript-eslint/recommended"], // Uses the linting rules from @typescript-eslint/eslint-plugin
  env: {
    node: true, // Enable Node.js global variables
  },
};
****\*****

// jest testing
touch jest.config.js
// enter the following
****\*\*****
module.exports = {
    preset: 'ts-jest',
    testEnvironment: 'node',
    "testPathIgnorePatterns": ["dist", "cypress/\*"]
};
****\*\*****
// change in package.json
"test": "jest",
"lint": "./node_modules/eslint/bin/eslint.js .eslintrc.json --ext .ts ./src/",