# CLAUDE.md

## Project Overview

**backtesting.py** is a Python framework for backtesting trading strategies. It provides a `Backtest` class and a `Strategy` base class for simulating trades on historical OHLCV data, computing performance statistics, and generating interactive plots.

## Repository Structure

```
backtesting/
  backtesting.py   # Core: Backtest, Strategy, Order, Trade, Position classes
  lib.py           # Utility indicators and helpers (crossover, etc.)
  _stats.py        # Performance statistics computation
  _plotting.py     # Bokeh-based interactive plotting
  _util.py         # Internal utilities
  test/            # Test data (GOOG.csv, EURUSD.csv) and test suite
doc/               # Documentation and Jupyter Notebook examples
```

## Development Setup

```bash
git clone git@github.com:kernc/backtesting.py
cd backtesting.py
pip3 install -e '.[doc,test,dev]'
```

## Common Commands

### Run Tests
```bash
python -m backtesting.test
```

### Linting
```bash
flake8
mypy backtesting
```

### Code Style (ruff)
```bash
ruff check backtesting
```

- Max line length: **100 characters**
- Config in `setup.cfg` (flake8/mypy) and `pyproject.toml` (ruff)

## Coding Guidelines

- Write unit tests for any new or changed functionality; tests live in `backtesting/test/_test.py`
- Follow existing code style — explicit commit messages, idiomatic Python
- Do not introduce regressions; run the full test suite before opening a PR
- Keep docstrings [pdoc](https://pdoc3.github.io/pdoc)-compatible for auto-generated documentation

## Key Classes

| Class | Location | Purpose |
|-------|----------|---------|
| `Backtest` | `backtesting/backtesting.py` | Orchestrates strategy simulation |
| `Strategy` | `backtesting/backtesting.py` | Base class users subclass to define strategies |
| `Order` / `Trade` / `Position` | `backtesting/backtesting.py` | Trade lifecycle objects |
| `crossover` | `backtesting/lib.py` | Common indicator utility |

## Pull Requests

- Open PRs against `master`
- Include a minimal working example that demonstrates the change
- Ensure `flake8`, `mypy`, and the test suite all pass
