---
title: "Why use let and const over var"
date: 2021-04-18T12:29:16-04:00
draft: false
tags: [javascript]
---

The way we hold onto things on a programming language is using variables. The classic explanation of what a variable is to imagine a box which can store things. The purpose is to retrieve those things at a later time.

## Introduction

In JavaScript, the variables can be declared using `var` or `const` and `let` keywords.

```js
var name = "John";
console.log("hello " + name);
```

There are some rules and conventions to follow.

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

The behavior described is concerning, although `message` works like a variable, it is not. It's a property of `window` object. This can be easily introduced by forgetting the `var` keyword. It can get worse, since we've the ability to overwrite the existing window object properties and methods.
