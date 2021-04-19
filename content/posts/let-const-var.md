---
title: "Why use let and const over var"
date: 2021-04-18T12:29:16-04:00
draft: false
tags: [javascript]
---

The way we hold onto things on a programming language is using variables. The classic explanation of what a variable is to imagine a box which can store things. The purpose is to retrieve those things at a later time.

## Introduction

In JavaScript, the variables can be declared using `var` or `const` and `let` keywords. Let's start with `var`. Here's an example of how variable is declared using `var` keyword.

```js
var name = "John";
console.log("hello " + name);
```

There are some rules and conventions to follow when declaring variables.

- The variable names can contain only letters, numbers and the symbol `$` and `_`
- The first character must not be a number.
- Reserved words cannot be used as variable names. For example `var` can cannot be used as a variable name.
- variable names are recommended to be written as `camelCase`

## Strict mode

Consider the below code.

```js
message = "hello world";
console.log(message);
```

There was no `var` keyword given, however when we execute this code it does not fail. What has happened is that this variable is attached to the global `window` object. To see that our variable is attached to the `window`, we can do the below.

```js
console.log(window.message);
```

The behavior described is concerning, although `message` works like a variable, it is not. It's a property of `window` object. This can be easily introduced by forgetting the `var` keyword. It can get worse, since we've the ability to overwrite the existing window object properties and methods. Below is an example of overwriting `console` property.

```js
console.log("hello world");
console = "hello world";
console.log("hello world"); // throws Uncaught TypeError
```

So, how do we fix this behavior. Enter `strict` mode. In a nutshell, `strict` mode throws more errors to avoid any quirks of the language.

Example of `strict` mode usage:

```js
"use strict";
name = "John"; // throws ReferenceError
```

## Hoisting

The variable declared using `var` are hoisted. This means that the JavaScript engine sees as if the variable is declared on the top, not the value. In other words, we could access a variable before it was even declared.

```js
console.log(name); // undefined
var name = "John";
console.log(name);
```

Even with `strict` mode, this behavior does not change.

## const and let

There is another way to declare variables in JavaScript. That is using `const` and `let` keywords.

- Unlike `var`, the variables declared with `const` and `let` keywords are not hoisted.
- When the value declared in a variable is not going to change use `const`
- When the value declared in a variable is going to change use `let`

Code sample to demonstrate variable declared using `const` and `let` are not hoisted.

```js
console.log(name); // throws ReferenceError
const name = "John";
```

Code sample of `let` usage.

```js
let age = 24;
age = 25
console.log(age);
```

Code sample of `const` usage.

```js
const age = 24;
age = 25 // throws Uncaught TypeError
console.log(age);
```

## const or let

So, what should be used to declare our variables? In most cases, `const` is the right choice. Given that it has more restrictions, the code is more readable.

- `const` should be declared with a value.
- variable declared with `const` as seen above cannot be reassigned.

## Conclusion

- Code readability matters.
- Use `const` and `let` over `var` when declaring variables.
- Use `let` only when there is a need for reassigning values.
- Use `camelCase` conventions when declaring variables for consistency.
