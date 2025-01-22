## Flux Programming Language Specification

**(January 21, 2025)**

This document serves as an informal specification and proposal for a new programming language.

## Overview

Flux is a new programming language designed as an alternative to Go, combined with the scripting capabilities of Bash. Its primary goal is to enable efficient development of compiled programs, such as servers. The language is built with speed and performance in mind, ensuring that the compiler and runtime environment operate with optimal efficiency.

## Program Description

A Flux program consists of one or more packages. Among these, a default package named `main` acts as the entry point of execution. If the `main` package contains a `.init()` function, this function will always be executed before the `.main()` function.

Each compilation unit in Flux is composed of:

1. A **package declaration**.
2. Optional **import statements**.
   - The number of imported packages does not affect the priority of execution.

Flux programs include various elements such as packages (dependent or independent), types, functions, and more. Individual packages can be defined in a separate file, exported for reuse, and explicitly imported into other compilation units.

The scoping rules in Flux are fundamentally similar to those in Go.

## Key Features

- **Efficient and performant**: Designed for building fast, compiled applications like servers.
- **Package structure**: Encourages modularity through well-defined packages.
- **Explicit imports**: Packages must be explicitly imported into each compilation unit where they are used.

Flux aims to combine the robustness of Go with the flexibility of Bash, providing developers with a powerful yet lightweight tool for building high-performance software.

# Symbol Explanation in Flux

In Flux, various symbols and operators serve specific purposes in programming. These symbols enable developers to perform arithmetic calculations, assign values, compare data, manipulate logic, and more. This guide provides a concise overview of each operator's role and usage within Flux, showcasing their significance in simplifying and enhancing the coding process.

## Arithmetic Operators

- `+` : Addition or string concatenation.
- `-` : Subtraction.
- `*` : Multiplication.
- `/` : Division.
- `%` : Modulus (remainder).
- `**` : Exponentiation.

## Assignment Operators

- `=` : Assign a value.
- `+=` : Add and assign.
- `-=` : Subtract and assign.
- `*=` : Multiply and assign.
- `/=` : Divide and assign.
- `%=` : Modulus and assign.

## Comparison Operators

- `==` : Loose equality (value only).
- `===` : Strict equality (value and type).
- `!=` : Loose inequality (value only).
- `!==` : Strict inequality (value and type).
- `>` : Greater than.
- `<` : Less than.
- `>=` : Greater than or equal to.
- `<=` : Less than or equal to.

## Logical Operators

- `&&` : Logical AND.
- `||` : Logical OR.
- `!` : Logical NOT.
- `??` : Nullish coalescing (default value when `null` or `undefined`).

## Bitwise Operators

- `&` : Bitwise AND.
- `|` : Bitwise OR.
- `^` : Bitwise XOR.
- `~` : Bitwise NOT.
- `<<` : Bitwise left shift.
- `>>` : Bitwise right shift.

## Other Operators

- `()` : Grouping or function invocation.
- `[]` : Array creation or access to elements.
- `{}` : Object creation or code block.
- `typeof` : Check the type of a value.
- `instanceof` : Check if an object is an instance of a class.
- `in` : Check if a property exists in an object.
- `...` : Spread or rest operator.
- `:` : Used in objects or conditional expressions (`? :`).

## Special Use Cases

- `?.` : Optional chaining to safely access nested properties.
- `:` : Object property assignment or part of a ternary operator.

By understanding and leveraging these symbols, developers can write efficient, clean, and robust code. Each operator is a building block of functionality, empowering programmers to solve complex problems and create innovative solutions in Flux. Mastering their usage is a key step toward becoming proficient in this versatile language.
