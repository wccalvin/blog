---
title: "How to execute a basic C++ program"
date: 2023-04-02
tags:
  - c++
  - execute c++ program
  - execute g++
  - hello world
---

## Introduction

To execute a C++ program,
  - we need to write a program
  - we need to know how to execute a compiler (with a inherent process of choosing a compiler and editor)

## Compiler and Editor

I think [vs-code](https://code.visualstudio.com/docs/languages/cpp) is a good place to start.
I use wsl2/ubuntu/g++ on my windows machine and clang on my mac.

## First Program

I've three versions of the `hello world` program. The only difference is with the namespace variations.

- not using `namespace` keyword.
  ```c++
  #include <iostream>

  // first program
  int main()
  {
    std::cout << "hello, world!" << std::endl;
    return 0;
  }
  ```

- `using namespace std;` scope.
  ```c++
  #include <iostream>

  using namespace std;

  // first program
  int main()
  {
      cout << "hello, world!" << endl;
      return 0;
  }
  ```

- using namespace restricted to the keyword scope.
  ```c++
  #include <iostream>

  using std::cout;
  using std::endl;

  /* first
   * program
  */
  int main()
  {
      cout << "hello, world!" << endl;
      return 0;
  }
  ```

## Program Structure

- `#` in `#include <iostream>` is a preprocessor directive and it's processed
  before actual compilation. The purpose of the directive is to prepare the
  program for compilation.
- `include` keyword is used to import libraries.
  - standard library names are enclosed in `<>`
  - user-defined library names are enclosed in `""`
  - the line is not terminated with `;`
- every c++ program has one main function which serves as an entry point.
- single line comments `// this is a one line comment`
- multi line comments
  ```c++
  /*
  this is a multi-line comment
  1 ...
  2 ...
  */
  ```
- `::` is a scope resolution operator.
- `cout` - standard output stream
- `<<` - insertion operator for output streams
- `cin` - standard input stream
- `>>` - extraction operator for input streams

## How to execute C++ program

- Compile the program: `g++ main.cpp -o hello`
- Execute the program: `./hello`

## References

- [Codecademy: C++ for Programmers](https://www.codecademy.com/learn/c-plus-plus-for-programmers)
- [Udacity: C++ for Programmers](https://learn.udacity.com/courses/ud210)
- [Begining C++ Programming - From Beginner to Beyond](https://www.udemy.com/course/beginning-c-plus-plus-programming/)
