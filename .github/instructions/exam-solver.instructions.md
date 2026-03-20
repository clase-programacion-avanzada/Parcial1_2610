---
description: Use this instructions file everytime you are asked to solve any code. Follow the instructions carefully and provide detailed explanations for your answers.
---
In the [README.md](../../README.md) file, you will find the details of the exam you need to solve. When solving, strictly you need to adhere to this topics:

permitted_topics:

  - topic: "Functions"

    subtopics: ["Definition and declaration", "Return types and parameters", "Function overloading", "Pass-by-value", "Pass-by-reference"]

  - topic: "Structs"

    subtopics: ["Declaration and usage", "Structs as function parameters", "Nested structs"]

  - topic: "Header Files"

    subtopics: ["Purpose of .h and .cpp files", "Include guards", "Avoiding circular dependencies"]

  - topic: "Pointers (Fundamentals Only)"

    subtopics: ["Declaration and initialization", "Heap vs. Stack memory", "Dereferencing", "Dynamic memory (new/delete)", "Dynamic arrays", "Basic pointer arithmetic for array traversal"]

  - topic: "C-Strings (from `<cstring>`)"

    subtopics: ["Concept of null-terminated character arrays", "Using standard library functions: strlen, strcpy, strcat, strcmp", "Reading C-strings from input", "Understanding buffer overflows and basic safety"]

  - topic: "References"

    subtopics: ["Reference variables", "Comparison to pointers", "Use in function parameters"]

  - topic: "C++ Strings (`std::string`)"

    subtopics: ["Basic usage of std::string", "Common operations: concatenation, comparison, find, substr, length", "Contrasting with C-strings"]

  - topic: "File I/O"

    subtopics: ["fstream for text files (read/write)", "fstream for binary files (read/write)", "Basic file operations (open, close, checking state)"]

In the exam, when they are referring to dynamic arrays, they are referring to arrays created using pointers and dynamic memory allocation (using `new` and `delete`).

When creating your plan, make sure your first step is to create the boilerplate code for the exam before writing the current functions. Be explicit using comments on which part of the code is the boilerplate and which part is the actual solution to the exam. This will help you stay organized and ensure that you are following the instructions correctly.

Also, use comments to explain your thought process and the reasoning behind your code. This code is intended to be educational, so providing detailed explanations will help others understand the concepts and techniques you are using.

All comments must be in spanish.

When tokenizing strings, do not use strtok. Instead, use a safer alternative that does not modify the original string and handles edge cases more robustly. You can use `std::istringstream` from the `<sstream>` library to parse the string safely.

In all the exams, they mention you must use pointer notation to access elements in arrays. You are allowed to use array indexing for readability.