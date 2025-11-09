# unitest

An English wrapper for the Portuguese [uniteste](https://github.com/angelonuffer/uniteste) testing framework for the [0 programming language](https://github.com/angelonuffer/0).
It allows grouping test suites, making assertions, and printing a summary of the results.

## equals : function

`values : list< number | text >` => `unitest : object`

Compares two values (simple equality).

## lists_equal : function

`lists : list<list< number | text >>` => `unitest : object`

Compares lists element by element.

## describe : function

`{ name : text tests : list<unitest> }` => `unitest : object`

Groups tests under a name.

## display : function

`unitest : object` => `code : text`

Receives an object in the unitest format and returns the Node.js code to execute the tests.

- The process prints messages per test and returns exit code `0` if all passed, or `1` otherwise.
- Failure messages describe the obtained value and the expected value.

## unitest : object

- `passed : number` - Number of tests that passed.
- `messages : list<list<text>>` - Messages returned by the tests.