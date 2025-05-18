# Pre-commit configuration (isort, black, flake8)

This repository contains a simple configuration to use `pre-commit` with three Python tools:

- `isort`] (https://pycqa.github.io/isort/) : automatically sorts imports
- [`black`] (https://black.readthedocs.io/) : format Python code
- `flake8`] (https://flake8.pycqa.org/) : checks code for best practices and errors

## Example: pre-commit demo

Here's a simple function, deliberately badly formatted, to illustrate what the `pre-commit` hooks detect:

### Before (source code with errors)
```
python
import math,sys,os
import numpy as np

def square_root(x):
 if x> 0:#x must be positive
 return math.sqrt(x)
```

### Error during commit

Errors detected :

**isort** :
- Incorrect grouping of imports
- Incorrect order

**black** :
- Incorrect spaces (`x> 0`, `return ...`)
- Bad general formatting

**flake8** :
- Missing spaces after commas
- Comment without spaces (`#x`)
- Imports not used: `os`, `sys`, `numpy`

### After correction:
```
python
import math

def square_root(x):
 if x > 0: # x must be positive
 return math.sqrt(x)
```
