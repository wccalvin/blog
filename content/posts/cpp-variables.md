---
title: "C++ -> how to declare a variable"
date: 2023-04-09T21:00:05-04:00
tags:
  - c++
  - variables
draft: true
---

## Definition

A variable is an abstraction for a memory location. Variable allows for meaningful names
instead of a memory address.

## Syntax

```text
<DataType> <VariableName> = <Value>;
```

## Examples

```c++
int rank = 1;
```

We can also declare multiple variables in a single statement, provided they're of the same
type.

```c++
int rankOne, rankTwo, rankThree = 0;
```

```c++
// example of uninitialized variable
int x;
```

```c++
// Example of initialized variable
int x = 5;  // C-like
int y {7};  // C++ 11 and above
```

```c++
// constant variable: should be initialized with the value and does not allow the value to be changed

const MAX_SCORE = 100;
```

## Good Practices

- Choose meaningful names over short form.
- Be consistent with the styling (cameCase or snake_case)
- Never use variables before initializing them.
- Declare variables only when you need them.
