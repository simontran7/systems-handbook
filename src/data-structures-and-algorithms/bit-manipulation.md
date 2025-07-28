# Bit Manipulation

## Basic Bitwise Operators

### Bitwise `NOT`

#### Syntax

`!a`

#### Behaviour

The output is the inverted input (i.e. `0` becomes `1` and `1` becomes `0`).

```
Input | Output
------|-------
  1   |   0
  0   |   1
```

### Bitwise `AND`

#### Syntax

`a & b`

#### Behaviour

If both inputs are a `1`, the output is a `1`.

```
Input 1 | Input 2 | Output
--------|---------|-------
   0    |    0    |   0
   1    |    0    |   0
   0    |    1    |   0
   1    |    1    |   1
```

### Bitwise `OR`

#### Syntax

`a | b`

#### Behaviour

If at least one input is a `1`, the output is a `1`.

```
Input 1 | Input 2 | Output
--------|---------|-------
   0    |    0    |   0
   1    |    0    |   1
   0    |    1    |   1
   1    |    1    |   1
```

### Bitwise `XOR`

#### Syntax

`a ^ b`

#### Behaviour

If exactly one input is a `1`, then the output will be a `1`.

```
Input 1 | Input 2 | Output
--------|---------|-------
   0    |    0    |   0
   1    |    0    |   1
   0    |    1    |   1
   1    |    1    |   0
```

### Bitwise Left Shift

#### Syntax

`n << k`, where `n`, `k` are integers.

#### Behaviour

Shifts the bits of an integer $n$ towards the left by \\(k\\) places, and filling the bottom \\(k\\) bits with zeroes.

Mathematically, `n << k` is equivalent to \\(n \cdot 2^k\\).

### Bitwise Right Shift

#### Syntax

`n >> k`, where `n`, `k` are integers.

#### Behaviour

Shifts the bits of an integer $n$ towards the right by \\(k\\) places, and filling the top \\(k\\) bits with zeroes.

Mathematically, `n >> k` is equivalent to \\(\lfloor\frac{n}{2^k}\rfloor\\).

## Bit Mask

A **bit mask** is a sequence of bits used to set, clear, or isolate specific bits in another value using bitwise operators.

The bit mask is typically a constant integer matching the same length as the value which we're masking on.