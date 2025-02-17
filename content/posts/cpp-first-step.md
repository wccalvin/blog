---
title: "Execute a C++ program using g++ CLI"
date: 2023-04-02
tags:
  - c++
---

## Choice of compiler and editor

I think [vs-code](https://code.visualstudio.com/docs/languages/cpp) is a good place to start.
My setup is wsl2/ubuntu/g++ on windows machine and clang on mac.

## First Program

Below are three versions of the `hello world` program.

### not using `namespace` keyword.
  ```c++
  #include <iostream>

  // first program
  int main()
  {
    std::cout << "hello, world!" << std::endl;
    return 0;
  }
  ```

### `using namespace std;` scope.
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

### using namespace restricted to the keyword scope.
  ```c++
  #include <iostream>

  using std::cout;
  using std::endl;

  /* multi line comment example:
   * first program
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
- [Beginning C++ Programming - From Beginner to Beyond](https://www.udemy.com/course/beginning-c-plus-plus-programming/)
