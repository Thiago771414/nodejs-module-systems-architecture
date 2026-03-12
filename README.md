# Node.js Module Systems Architecture Guide

![Project Type](https://img.shields.io/badge/Project%20Type-Backend%20Architecture%20Case%20Study-purple)
![Node.js](https://img.shields.io/badge/Runtime-Node.js-green)
![JavaScript](https://img.shields.io/badge/Language-JavaScript-yellow)
![Modules](https://img.shields.io/badge/Concept-Module%20Systems-blue)
![Architecture](https://img.shields.io/badge/Focus-Backend%20Fundamentals-orange)

---

# Node.js Module Systems Architecture

This repository demonstrates how **JavaScript module systems work in Node.js**, comparing the traditional **CommonJS** approach with the modern **ECMAScript Modules (ESM)**.

The project explores how modules are:

- defined
- imported
- exported
- executed

in different Node.js module systems.

This serves as a **backend engineering case study** focused on understanding Node.js runtime behavior.

---

# Case Study

## Problem

Node.js historically used **CommonJS** as its module system, while modern JavaScript standards introduced **ECMAScript Modules (ESM)**.

Developers often face challenges when:

- migrating legacy Node.js applications
- mixing CommonJS and ES Modules
- configuring module resolution
- managing package.json module types

Without understanding these differences, projects can encounter runtime errors and compatibility issues.

---

## Solution

This repository demonstrates how both module systems operate and how they can be configured in Node.js environments.

The project includes examples for:

- CommonJS modules
- ECMAScript modules
- module export/import patterns
- Node.js configuration strategies

It provides a practical reference for understanding how JavaScript module systems work internally.

---

# Architecture

The module system defines how dependencies are loaded and executed.

```text
Application
│
▼
Module Loader
│
├── CommonJS
│ ├─ require()
│ └─ module.exports
│
└── ECMAScript Modules
├─ import
└─ export
```

Both systems enable modular architecture but use different loading mechanisms.

---

# CommonJS Module Example

CommonJS is the historical module system used by Node.js.

```javascript
// lib.js
function soma(a, b) {
  return a + b;
}

module.exports = { soma };
```
Using the module:
```js
const { soma } = require('./lib');

console.log(soma(2,3));
```
## Characteristics:

synchronous module loading

require syntax

module.exports for exports

# ECMAScript Modules (ESM)

ES Modules are the modern JavaScript standard module system.
```js
// lib.mjs
function soma(a, b) {
  return a + b;
}

export { soma };
```
Using the module:
```js
import { soma } from './lib.mjs';

console.log(soma(2,3));
```
Characteristics:

standardized module syntax

static import analysis

tree-shaking support

# Enabling ES Modules in Node.js

Two main strategies can enable ES Modules.

Strategy 1: .mjs extension

Files using ES modules can use the .mjs extension.
```text
node app.mjs
```
# Strategy 2: package.json configuration

Add the module type in package.json.
```js
{
  "name": "my-app",
  "version": "1.0.0",
  "type": "module"
}
```
This allows .js files to use ES module syntax.

# Folder Structure

Example project structure:
```text
nodejs-module-systems-architecture
│
├── commonjs
│   ├── lib.js
│   └── app.js
│
├── esm
│   ├── lib.mjs
│   └── app.mjs
│
├── package.json
│
└── README.md
```
This structure separates examples for each module system.

# How to Run

Clone the repository:
```text
git clone
```
Navigate to the project:
```text
cd nodejs-module-systems-architecture
```
Run CommonJS example:
```text
node commonjs/app.js
```
Run ES Module example:
```text
node esm/app.mjs
```

# Learning Outcomes

Developers studying this repository will understand:

Node.js module systems

differences between CommonJS and ESM

module import/export patterns

Node.js module resolution behavior

migration strategies between module systems

# Technologies

Node.js

JavaScript

CommonJS

ECMAScript Modules

# Author

Thiago Reis Lima
Linkedin:
```text
https://www.linkedin.com/in/thiago-lima-2a5896166/
```
