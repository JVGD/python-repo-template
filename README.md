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
- **🔧 Development Tools**: Pre-configured for immediate productivity

## 📋 Prerequisites

Before using this template, ensure you have the following installed:

### Required Tools

| Tool | Version | Purpose | Installation |
|------|---------|---------|--------------|
| uv | >=0.8.22 | Package manager | [uv installation](https://docs.astral.sh/uv/getting-started/installation/) |
| Python | 3.11+ | Runtime environment | [python.org](https://www.python.org/downloads/) (can also be installed with `uv`) |
| Task | >=3.44.1 | Task runner (better than Makefiles)| [Taskfile](https://taskfile.dev/installation) |
| Docker | >=24.0.2 | Containerization | [Docker](https://www.docker.com/get-started/) |

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
# Creating .env file
task env

# Install all dependencies (including development tools)
task install

# Verify installation running full quality assurance pipeline
task qa
```

### 3. ✏️ Customize Your Project

Run the task `rename` to automatically rename the package template to your desired name.

```bash
# This task renames the template package to your desired name, handle directories files and imports
task rename NAME=your_package
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

# ⚡ Run complete quality assurance pipeline (format, lint, type_check and tests)
task qa

# 🧽 Clean generated files
task clean
```

### 🪝 Pre-commit Hooks

This template includes comprehensive pre-commit hooks for code quality. They are installed when running `task install`. However if you want to run it on all files ad-hoc you can issue:

```bash
# Run hooks on all files manually
pre-commit run --all-files
```

Included Hooks:
- **Python**: Ruff (linting & formatting)
- **General**: Trailing whitespace, end-of-file-fixer, merge conflict detection
- **YAML**: yamllint, prettier formatting
- **JSON**: prettier formatting, syntax validation

### 🐳 Docker

Build and run the project in a container:

```bash
# Build Docker image
task build

# Build with custom tag
task build TAG=my-app:v1.0.0
```

## 📁 Project Structure

```
python-repo-template/
├── 📄 .dockerignore           # Docker ignore patterns
├── 📄 .env.example            # Environment variables template
├── 📄 .gitignore              # Git ignore patterns
├── 📄 .pre-commit-config.yaml # Pre-commit hooks configuration
├── 📄 .python-version         # Python version specification
├── 📄 Dockerfile              # Docker container definition
├── 📄 LICENSE                 # Project license
├── 📄 pyproject.toml          # Project metadata & tool configuration
├── 📄 README.md               # Project documentation
├── 📄 Taskfile.yml            # Task automation definitions
├── 📄 uv.lock                 # Dependency lock file
├── 📁 .venv/                  # Virtual environment (auto-created)
├── 📁 src/                    # Source code (importable package)
│   ├── 📄 main.py             # Main application entry point
│   └── 📁 template_package/   # Example package (rename to your package)
│       ├── 📄 __init__.py
│       └── 📄 template_module.py
└── 📁 tests/                  # Test suite
    ├── 📄 __init__.py
    ├── � test_main.py        # Tests for main.py
    └── 📁 template_package/   # Package-specific tests
        ├── 📄 __init__.py
        └── 📄 test_template_module.py
```

### 🧑‍⚖️ License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
