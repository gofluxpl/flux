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
