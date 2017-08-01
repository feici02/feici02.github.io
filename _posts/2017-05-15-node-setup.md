---
layout: post
title: "Setup Your First Node.js Project"
tags: node.js
---

Here are my steps to setup a working Node.js environment from scratch.

## 1. Install nvm (Node Version Manager)
Please refer to the README of this [project](https://github.com/creationix/nvm) for installation.

## 2. Install node and npm with nvm
```
nvm install node
```

## 3. Verify installation
```
node -v
npm -v
```

## 4. Create the first Node project
```
mkdir node-project
cd node-project
npm init

# install dependency locally and add it to package.json
npm install left-pad --save
```

## 5. Create index.js
```
const leftPad = require('left-pad');         // Require left pad
const output = leftPad('Hello, World!', 15); // Define output

// Send output to the console
console.log(output);
```

## 6. Run
```
node index.js
```
"Hello, World!" is printed on the console with two spaces on the left. 

## 7. Reference
1. <https://www.taniarascia.com/how-to-install-and-use-node-js-and-npm-mac-and-windows/>
