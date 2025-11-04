# unitest

An English wrapper for the Portuguese [uniteste](https://github.com/angelonuffer/uniteste) testing framework for the [0 programming language](https://github.com/angelonuffer/0).

## Overview

`unitest` provides an English API that delegates to `uniteste`, translating parameters from English to Portuguese and results from Portuguese to English.

## API

### Functions

- `unitest.describe({ name tests })`: Groups tests under a name. Returns an object that can be displayed or nested.
- `unitest.equals([obtained expected])`: Compares two values (simple equality) and generates success or failure message.
- `unitest.lists_equal([list1 list2])`: Compares lists element by element and generates appropriate message.

### API Translation

| English (unitest) | Portuguese (uniteste) |
|-------------------|----------------------|
| `describe`        | `descrever`          |
| `equals`          | `iguais`             |
| `lists_equal`     | `listas_iguais`      |
| `name`            | `nome`               |
| `tests`           | `testes`             |

## Example

```0
unitest = https://cdn.jsdelivr.net/gh/angelonuffer/unitest@main/código/0

unitest.describe({
  name: "Arithmetic"
  tests: [
    unitest.equals([(1 + 1) 2])
    unitest.equals([(2 + 3) 5])
  ]
})
```

## Running Tests

**Prerequisites**: Node.js version 22 or higher and the [0 language runtime](https://github.com/angelonuffer/0).

```bash
node 0/código/0_node.js testes/equals.0 | node
```

## Output

- The test runner prints messages per test and returns exit code `0` if all passed, or `1` otherwise.
- Failure messages describe the obtained value and the expected value in English.

Examples:
- Success: `ok`
- Failure: `Expected 5 to equal 6.`
- Summary: `2/2 tests passed.`