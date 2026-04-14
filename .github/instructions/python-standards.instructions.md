---
description: 'Python code standards and best practices. Applied automatically to all Python files.'
applyTo:
  - '**/*.py'
---

# Python Development Standards

When writing or reviewing Python code, follow these guidelines:

## Code Style

- Follow PEP 8 style guide
- Use Black formatter defaults (88 char line length)
- Import order: stdlib, third-party, local (separated by blank lines)
- Use f-strings for string formatting (Python 3.6+)
- Prefer list/dict comprehensions for simple transformations

## Type Hints

- Add type hints to all function signatures
- Use `typing` module for complex types
- Type hint return values including `None`
- Use `Optional[T]` for nullable values
- Consider using `Protocol` for duck typing

Example:
```python
from typing import List, Optional

def process_items(items: List[str], limit: Optional[int] = None) -> List[str]:
    return items[:limit] if limit else items
```

## Error Handling

- Use specific exceptions, not bare `except:`
- Raise exceptions early (fail fast)
- Document exceptions in docstrings
- Clean up resources with context managers (`with` statements)

## Documentation

- Use docstrings for all public functions, classes, and modules
- Follow Google or NumPy docstring format
- Include usage examples in docstrings
- Document parameters, returns, and raises

Example:
```python
def calculate_total(prices: List[float], tax_rate: float) -> float:
    """Calculate total price including tax.
    
    Args:
        prices: List of item prices
        tax_rate: Tax rate as decimal (e.g., 0.08 for 8%)
    
    Returns:
        Total price including tax
        
    Raises:
        ValueError: If tax_rate is negative
    """
    if tax_rate < 0:
        raise ValueError("Tax rate cannot be negative")
    subtotal = sum(prices)
    return subtotal * (1 + tax_rate)
```

## Testing

- Use pytest as the testing framework
- Test file naming: `test_*.py` or `*_test.py`
- Use fixtures for shared setup
- Aim for 80%+ code coverage
- Test edge cases and error conditions

## Modern Python Features

Prefer modern Python features when appropriate:

- **Dataclasses** (3.7+) for data containers
- **Pathlib** for file operations instead of `os.path`
- **Walrus operator** (3.8+) for assignment expressions
- **Match statements** (3.10+) for structural pattern matching
- **Type hints** with Union types using `|` (3.10+)

## Common Patterns

### Configuration
```python
from dataclasses import dataclass
from pathlib import Path

@dataclass
class Config:
    base_path: Path
    debug: bool = False
    timeout: int = 30
```

### Context Managers
```python
from contextlib import contextmanager

@contextmanager
def temporary_setting(config, key, value):
    old_value = getattr(config, key)
    setattr(config, key, value)
    try:
        yield
    finally:
        setattr(config, key, old_value)
```

### Async/Await
```python
async def fetch_data(url: str) -> dict:
    async with aiohttp.ClientSession() as session:
        async with session.get(url) as response:
            return await response.json()
```

## Anti-Patterns to Avoid

- ❌ Mutable default arguments: `def func(items=[])`
- ❌ Bare except clauses: `except:`
- ❌ Global variables for state
- ❌ `from module import *`
- ❌ Not using virtual environments
- ❌ Ignoring type hints
- ❌ Copy-paste code instead of functions

## Dependencies

- Use `pyproject.toml` for project configuration (PEP 518)
- Pin versions in `requirements.txt` or `poetry.lock`
- Separate dev dependencies from runtime dependencies
- Keep dependencies minimal and audit regularly

## Project Structure

```
project/
├── src/
│   └── package/
│       ├── __init__.py
│       ├── module.py
│       └── subpackage/
├── tests/
│   ├── __init__.py
│   └── test_module.py
├── pyproject.toml
├── README.md
└── .gitignore
```
