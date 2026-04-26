# Project README

## Overview
This project is a C implementation of an A* Path Finder algorithm, which allows users to find the shortest path in a grid. The GUI can be built and run on multiple platforms including Linux, Windows, WebAssembly, and Wine.

## Features
- Basic A* Path Finding Algorithm
- Graphical User Interface (GUI)
- Cross-platform support using Makefiles for different environments

## Project Structure
```
Gui_ASTAR/
├── build/              # .exe files produced by Main.c
├── src/                # src code
│   ├── Main.c          # Entry point
│   └── *.h             # stand alone Header-based C-files, without *.c files that implement it
├── Makefile.linux      # Linux Build configuration
├── Makefile.windows    # Windows Build configuration
├── Makefile.wine       # Wine Build configuration
├── Makefile.web        # Emscripten Build configuration
└── README.md           # This file
```

## Prerequisites
- C/C++ Compiler and Debugger (GCC, Clang)
- Make utility
- Standard development tools
- Libraries needed in specific projects:
  - For Linux: X11, PNG, JPEG
  - For Windows: user32, gdi32, winmm
  - For WebAssembly: emcc

## Build & Run
### Building on Linux
To build the project for Linux:
```bash
cd Gui_ASTAR/
make -f Makefile.linux all
```
To execute the built application:
```bash
make -f Makefile.linux exe
```

### Building on Windows
To build the project for Windows:
```cmd
cd Gui_ASTAR\
mingw32-make -f Makefile.windows all
```
To execute the built application:
```cmd
mingw32-make -f Makefile.windows exe
```

### Building on WebAssembly
To build the project for WebAssembly:
```bash
cd Gui_ASTAR/
emmake make -f Makefile.web all
```
To run the WebAssembly file in a browser:
```bash
emrun --no_browser --port 8080 build/index.html
```

### Building on Wine
To build the project for Windows using Wine:
```bash
cd Gui_ASTAR/
WINEPREFIX=~/wine64 WINEARCH=win64 mingw32-make -f Makefile.wine all
```
To run the built application:
```bash
WINEPREFIX=~/wine64 WINEARCH=win64 wine build/Main.exe
```