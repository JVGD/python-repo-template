# 🐍 Python Repository Template

> A comprehensive, production-ready template for Python projects with modern tooling, automated code quality, and best practices baked in.

[![Python](https://img.shields.io/badge/python-3.11%2B-blue.svg)](https://www.python.org/downloads/)
[![Code style: Ruff](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/astral-sh/ruff/main/assets/badge/v2.json)](https://github.com/astral-sh/ruff)
[![Type checking: mypy](https://img.shields.io/badge/type%20checking-mypy-blue)](https://mypy.readthedocs.io/)
[![Testing: pytest](https://img.shields.io/badge/testing-pytest-blue)](https://pytest.org/)
[![Task runner: Taskfile](https://img.shields.io/badge/task%20runner-Taskfile-blue)](https://taskfile.dev/)

## ✨ Features

This template provides a complete development environment with:

- **🏗️ Modern Build System**: Uses `pyproject.toml` with setuptools backend
- **📦 Dependency Management**: UV for ultra-fast package management
- **🎯 Code Quality**: Ruff for linting and formatting (replaces Black + isort + flake8)
- **🔍 Type Checking**: MyPy with strict configuration
- **🧪 Testing Framework**: pytest with coverage reporting and markers
- **🪝 Pre-commit Hooks**: Automated code quality checks for Python, YAML, and JSON
- **⚡ Task Automation**: Taskfile for common development tasks
- **📁 Src Layout**: Modern Python package structure
- **🔧 Development Tools**: Pre-configured for immediate productivity

## 📋 Prerequisites

Before using this template, ensure you have the following installed:

### Required Tools

| Tool | Version | Purpose | Installation |
|------|---------|---------|--------------|
| **Python** | 3.11+ | Runtime environment | [python.org](https://www.python.org/downloads/) |
| **UV** | Latest | Package manager | [uv installation](https://docs.astral.sh/uv/getting-started/installation/) |
| **Task** | Latest | Task runner | [taskfile.dev/installation](Task installation/) |

## 🚀 Quick Start

### 1. 📥 Clone or Use Template

```bash
# Using GitHub CLI
gh repo create my-awesome-project --template JVGD/python-repo-template

# Or clone directly
git clone https://github.com/JVGD/python-repo-template.git my-awesome-project
cd my-awesome-project
```

### 2. 🔧 Initialize Project

```bash
# Install all dependencies (including development tools)
task install

# Verify installation
task help
```

### 3. ✏️ Customize Your Project

Edit these key files to match your project:

```bash
# Update project metadata
vim pyproject.toml  # Change name, description, author

# Update package name
mv src/template_package src/your_package_name
mv tests/template_package tests/your_package_name

# Update imports in test files
find tests/ -name "*.py" -exec sed -i 's/template_package/your_package_name/g' {} \;
```

## 🛠️ Development Workflow

### Core Commands

```bash
# 📦 Install dependencies
task install

# 🧹 Format code (runs Ruff formatter)
task format

# 🔍 Lint code (runs Ruff linter with auto-fix)
task lint

# 🏷️ Type check (runs MyPy)
task type_check

# 🧪 Run tests
task test

# ⚡ Run complete quality assurance pipeline
task qa

# 🧽 Clean generated files
task clean
```

### 🪝 Pre-commit Hooks

This template includes comprehensive pre-commit hooks for code quality:

```bash
# Install pre-commit hooks (run once after cloning)
pre-commit install

# Run hooks on all files manually
pre-commit run --all-files

# Run hooks on staged files only
pre-commit run

# Update hook versions
pre-commit autoupdate
```

**Included Hooks:**
- **Python**: Ruff (linting & formatting), MyPy (type checking), Bandit (security)
- **General**: Trailing whitespace, end-of-file-fixer, merge conflict detection
- **YAML**: yamllint, prettier formatting
- **JSON**: prettier formatting, syntax validation
- **TOML**: syntax validation
- **Security**: Safety dependency checks, Bandit security linting

## 📁 Project Structure

```
my-awesome-project/
├── 📄 pyproject.toml          # Project metadata & tool configuration
├── 📄 Taskfile.yml            # Task automation definitions
├── 📄 uv.lock                 # Dependency lock file
├── 📁 src/                    # Source code (importable package)
│   └── 📁 your_package/
│       ├── 📄 __init__.py
│       └── 📄 module.py
├── 📁 tests/                  # Test suite
│   ├── 📄 __init__.py
│   └── 📁 your_package/
│       ├── 📄 __init__.py
│       └── 📄 test_module.py
└── 📁 .venv/                  # Virtual environment (auto-created)
```

## ⚙️ Tool Configuration

### 🎯 Ruff (Linting & Formatting)

Configured in `pyproject.toml` with:
- **Line Length**: 120 characters
- **Rules**: Pycodestyle, Pyflakes, isort, bugbear, pyupgrade
- **Auto-fix**: Enabled for safe transformations

### 🔍 MyPy (Type Checking)

Strict configuration enabled:
- **Strict Mode**: All optional checks enabled
- **Target**: `src/` and `tests/` directories
- **Python Version**: Matches project requirement (3.11+)

### 🧪 pytest (Testing)

Comprehensive test configuration:
- **Test Discovery**: `tests/` directory with `test_*.py` pattern
- **Coverage**: Minimum 80% threshold with HTML/XML reports
- **Markers**: `unit`, `integration`, `slow`, `smoke` for test categorization
- **Plugins**: pytest-cov, pytest-mock included

### ⚡ Task (Automation)

All development workflows automated:
- **Dependency Management**: Install, sync, clean
- **Code Quality**: Format, lint, type check
- **Testing**: Various test execution strategies
- **CI/CD**: Complete pipeline automation


### 🧑‍⚖️ License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
