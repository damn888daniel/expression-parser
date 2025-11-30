# Expression Parser - C++ with AST and Multithreading

A high-performance C++ expression parser supporting arithmetic operations, trigonometric functions, and mathematical expressions. Features Abstract Syntax Trees (AST), multithreaded evaluation, and CSV output.

## Features

- **Arithmetic Operations**: `+`, `-`, `*`, `/`
- **Trigonometric Functions**: `sin`, `cos`, `tan`, `ctan`, `arcsin`, `arccos`
- **AST Construction**: Full abstract syntax tree representation
- **Multithreading**: Concurrent expression evaluation using thread pools
- **CSV Output**: Results saved in structured CSV format
- **Large File Support**: Optimized streaming for 4+ GB data files
- **Error Handling**: Comprehensive error messages and validation
- **stdin Support**: Accepts expressions from standard input

## Build

```bash
mkdir build
cd build
cmake ..
make
```

## Usage

```bash
./expression_parser input.txt output.csv [num_threads]
./expression_parser - output.csv  # Read from stdin
```

## Input Format

Each line contains a mathematical expression to evaluate.

## Output Format

CSV with columns: `line,expression,status,result,message`

## Supported Functions

- `sin(x)` - Sine
- `cos(x)` - Cosine  
- `tan(x)` - Tangent
- `ctan(x)` - Cotangent
- `arcsin(x)` - Arc sine (domain: [-1, 1])
- `arccos(x)` - Arc cosine (domain: [-1, 1])

## Requirements

- C++20 compiler
- CMake 3.16+
- Threading library (Threads::Threads)
