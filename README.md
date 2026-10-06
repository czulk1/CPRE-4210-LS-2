# Buffer Overflow Educational Simulator

## Overview
This interactive web application is designed to visually demonstrate the mechanics of a stack-frame buffer overflow. It was created as an educational module to help learners understand how uncontrolled user input can leak out of an allocated buffer and overwrite adjacent memory on the stack.

## Features
- **Visual Memory Grid**: A simulated stack layout showing memory addresses, an 8-byte character buffer, a 4-byte Saved Frame Pointer (SFP), and a 4-byte Return Address.
- **Real-time Interaction**: As you type into the input field, the memory grid populates instantly byte-by-byte.
- **Color-coded Regions**: Green for safe buffer space, yellow for the SFP, and red for the highly critical Return Address.
- **Dynamic Threat Assessment**: A status dashboard updates to warn the user the exact moment their input corrupts the frame pointer or hijacks the return address.

## How to Run
This is a purely client-side static web application. There are no servers, dependencies, or build tools required.
1. Clone this repository or download the `index.html` file.
2. Double-click `index.html` to open it in any modern web browser (Chrome, Firefox, Safari, Edge).

## Educational Goal
The goal of this tool is not to teach exploitation, but rather *vulnerability mechanics*. By seeing exactly where variables live in relation to execution flow control data (the Return Address), developers can better understand why bounds checking (e.g., using `strncpy` instead of `strcpy`) is critical in languages like C and C++.