# STACKS_IMPLEMENTATION-
ASSIGNMENT(1)_FATMATA SILLAH_905004192_BIT2101_SEM(5)
# Stack-Based Expression Evaluator

**Course:** DCOMP320 – Data Structures and Algorithms
**Assignment:** Stacks Implementation (Version 2 – Postfix approach)
**Student:** Fatamata Sillah
**University:** Limkokwing University of Creative Technology

A Python program that reads arithmetic expressions from a text file, evaluates each one using stacks, and writes the results to a second text file in the same layout as the input.

## How it works

The stack is written from scratch as a singly linked list (`Node` and `Stack` classes), with `push`, `pop`, `peek`, `is_empty` and `size`. Popping or peeking an empty stack raises `IndexError`.

Each expression is evaluated in two steps:

1. **Infix to postfix (Shunting-Yard).** Numbers go straight to the output list. Operators wait on an operator stack until an operator with higher (or equal, for left-associative) precedence is popped off first. `(` is pushed, and `)` pops operators until the matching `(`.
2. **Postfix evaluation.** The postfix list is scanned left to right. Numbers are pushed onto an operand stack. An operator pops two operands (right first, then left), computes the result and pushes it back. The last value left is the answer.

Unary minus (for example `-3 + 5`) is detected while tokenizing and treated as a separate operator, `u-`, with the highest precedence.

## Project files

| File | Purpose |
| --- | --- |
| `expression_evaluator.py` | The program (standard library only) |
| `input.txt` | Sample input |
| `output.txt` | Sample output |
| `README.md` | This file |

## Requirements

- Python 3.6 or newer (uses f-strings)
- No third-party packages

## Usage

```bash
# Uses input.txt and output.txt in the current folder
python expression_evaluator.py

# Or give your own file names
python expression_evaluator.py my_input.txt my_output.txt
