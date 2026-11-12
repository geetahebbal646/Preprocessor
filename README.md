# Mini C Preprocessor Tool

This repository contains a lightweight, custom-built C preprocessor.[cite: 7] Designed as a systems programming project, it replicates the initial phases of a C compiler by handling directives and sanitizing source files before compilation, producing a clean `.i` output file.[cite: 7]

## Core Capabilities

* **1. Resolving `#include` Directives:** Detects inclusion statements and automatically embeds the content of standard header files (searching paths like `/usr/include/`) directly into the active source code.[cite: 7]
* **2. Dynamic `#define` Replacement:** Extracts macro names and their corresponding values, storing them in a linked list.[cite: 7] It then safely substitutes these macros throughout the file while actively ignoring text inside double quotes.[cite: 7]
* **3. Source Code Sanitization:** Scans the file character-by-character to detect and completely remove both inline (`//`) and block (`/* ... */`) comments.[cite: 7]
* **4. Intermediate File Processing:** Seamlessly handles file transitions using a temporary file (`temp.c`) to process the raw code before generating the final `.i` output.[cite: 7]

## Technical Implementation Details

* **A. Custom Linked List (SLL):** Replaces static arrays with a dynamically allocated Singly Linked List (`struct stu`) to store an unlimited number of macro definitions.[cite: 7]
* **B. File Pointers & I/O:** Makes extensive use of C file handling (`fopen`, `fseek`, `fgetc`, `rewind`) to accurately navigate and modify text files.[cite: 7]
* **C. Manual String Processing:** Utilizes custom-built functions (like `mystrcat`) alongside standard string library tools to accurately match and replace tokens.[cite: 7]
* **D. Heap Memory Management:** Allocates memory on the fly using `malloc()` to efficiently handle 2D arrays for reading lines of code, preventing memory waste.[cite: 7]

## Hardware & Circuitry

**N/A (Strictly Software)**
This is a 100% software-based systems programming tool written in standard C. It manipulates text files at the software level and does not require any microcontrollers, physical circuits, or hardware implementation.
