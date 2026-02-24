# Sorting Algorithm Optimizer (Stack-Based)

## Overview

This project implements an optimized integer sorting algorithm using a constrained
instruction set operating on two stacks.

The objective is to sort a list of integers using the smallest possible number of
operations, under strict stack-manipulation rules.

The project demonstrates:

- Algorithmic optimization
- Time and move complexity reduction
- Stack data structure manipulation
- Instruction cost minimization
- Performance benchmarking

---

## Problem Constraints

You are given:

- Stack A (unsorted integers)
- Stack B (empty)

You may only use the following operations:

### Swap
- `sa` – swap top two elements of stack A
- `sb` – swap top two elements of stack B
- `ss` – swap both

### Push
- `pa` – push top of B to A
- `pb` – push top of A to B

### Rotate
- `ra` – rotate A upward
- `rb` – rotate B upward
- `rr` – rotate both

### Reverse Rotate
- `rra` – rotate A downward
- `rrb` – rotate B downward
- `rrr` – rotate both

The goal is to sort Stack A in ascending order using the minimum number of moves.

---

## Algorithm Strategy

### Small Input Optimization (≤ 5 elements)

- Hardcoded optimal sequences
- Minimal-move decision trees

### Medium & Large Input Strategy

- Index normalization (coordinate compression)
- Binary radix sort strategy
- Bitwise sorting passes
- Stack B used as temporary buffer
- Stable reconstruction back to Stack A

This ensures:

- O(n log n) logical behavior
- Predictable move count scaling
- Deterministic output

---

## Data Structures

- Linked list implementation for stacks
- Indexed value mapping
- Operation dispatcher abstraction
- Move counter tracking

---

## Execution Flow

1. Parse and validate input
2. Normalize values
3. Choose strategy based on input size
4. Execute sorting routine
5. Output optimized instruction list

---

## Compilation

```
make
```

Produces:

```
./push_swap
```

---

## Usage

```
./push_swap 3 2 5 1 4
```

Outputs:

```
pb
ra
sa
pa
...
```

To verify correctness:

```
./push_swap 3 2 5 1 4 | ./checker 3 2 5 1 4
```

---

## Performance Characteristics

- 3 numbers → ≤ 3 moves
- 5 numbers → ≤ 12 moves
- 100 numbers → optimized under benchmark threshold
- 500 numbers → within competitive operation bounds

Move count scales efficiently due to radix-based partitioning.

---

## Error Handling

- Duplicate detection
- Non-integer validation
- Overflow protection
- Graceful exit on invalid input

---

## Key Concepts Demonstrated

- Stack-based computation
- Operation cost minimization
- Bitwise sorting techniques
- Algorithmic complexity control
- Memory-safe C programming

---

## What This Project Demonstrates

This implementation reflects:

- Strong understanding of algorithmic trade-offs
- Practical optimization under constraints
- Deterministic system behavior
- Low-level data manipulation

Applicable domains include:

- Embedded systems
- Performance-critical backends
- Algorithm research
- Systems-level tooling

---

## Author

Khaled Adas  
Systems Programming | Algorithm Optimization | C
