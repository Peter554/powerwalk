# fast-walk

[![PyPI](https://img.shields.io/pypi/v/fast-walk.svg)](https://pypi.org/project/fast-walk/)
[![CI](https://github.com/Peter554/fast-walk/actions/workflows/check.yml/badge.svg)](https://github.com/Peter554/fast-walk/actions/workflows/check.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Documentation](https://img.shields.io/badge/docs-latest-blue.svg)](https://peter554.github.io/fast-walk/)

Fast parallel directory walking for Python, powered by Rust.

- Find the repo [here](https://github.com/Peter554/fast-walk).
- Read the docs [here](https://peter554.github.io/fast-walk/).

## Features

- 🚀 **Fast**: Uses the rust [ignore](https://crates.io/crates/ignore) crate for fast directory traversal.
- ⚡ **Parallel**: Multi-threaded directory traversal.
- 🎯 **Smart filtering**: Built-in support for `.gitignore`, `.ignore`, and glob patterns.
- 🔒 **Type-safe**: Full type hints.

## Installation

```bash
pip install fast-walk
```

## Quick Start

```python
import fast_walk

# Find all Python files, respecting .gitignore
for entry in fast_walk.walk(".", filters=["*.py"]):
    if entry.is_file:
        print(entry.path)

# Custom configuration
for entry in fast_walk.walk(
    ".",
    filters=["*.yaml", "*.yml"],
    ignore_dirs=["node_modules", "venv"],
    max_depth=3,
    threads=4,
):
    print(entry.path_str, entry.is_dir)
```
