# Nimporter

![License](https://img.shields.io/github/license/Pebaz/Nimporter)

Compile [Nim](<https://nim-lang.org/>) extensions for Python on import automatically!

With Nimporter, you can simply import Nim source code files *as if they
were Python modules*, and use them seamlessly with Python code. The compiler is
invoked to build a Python-compatible extension module and it is then placed in
the `__pycache__` directory, which means that you don't have to add a line to
your `.gitignore` files because (presumably) Git is already ignoring the
`__pycache__` directory.

## Possible Benefits

 * Seamless integration with existing Nim code by using the
   [Nimpy](https://github.com/yglukhov/nimpy) library.
 * Very low effort to create high-performance Python extensions using Nim.
 * Leverage both language's ecosystems: Python for breadth, Nim for performance.

### Dependencies

 1. [Nim Compiler](<https://nim-lang.org/install.html>)
 2. [Nimpy library](https://github.com/yglukhov/nimpy)
 3. [Nimporter library](https://github.com/Pebaz/nimporter) (this library).

### Installation

```bash
# Windows
$ pip install git+https://github.com/Pebaz/nimporter  # Nimporter library
$ nimble install nimpy  # Nimpy library

# Everything Else
$ pip3 install git+https://github.com/Pebaz/nimporter  # Nimporter library
$ nimble install nimpy  # Nimpy library
```

### Examples

```nim
# nim_math.nim

import nimpy

proc add(a: int, b: int): int {.exportpy.} =
    return a + b
```

```python
import nimporter

import nim_math

print(nim_math.add(2, 4))  # 6
```

### Documentation

For tutorials, advanced usage, and more, head over to the [Wiki](<https://github.com/Pebaz/nimporter/wiki>).

### Stargazers over time

[![Stargazers over time](https://starchart.cc/Pebaz/nimporter.svg)](https://starchart.cc/Pebaz/nimporter)

> Made using <https://starchart.cc/>
