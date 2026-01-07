# Contributing to Python Code Visualizer

First off, thank you for considering contributing! 🎉

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Development Setup](#development-setup)
- [Pull Request Process](#pull-request-process)
- [Style Guidelines](#style-guidelines)

---

## 📜 Code of Conduct

This project adheres to a Code of Conduct. By participating, you are expected to uphold this code. Please be respectful and inclusive.

---

## 🤔 How Can I Contribute?

### 🐛 Reporting Bugs

Before creating bug reports, please check existing issues. When creating a bug report, include:

- **Clear title** describing the issue
- **Steps to reproduce** the behavior
- **Expected behavior** vs actual behavior
- **Python version** and OS
- **Code sample** that causes the issue

### 💡 Suggesting Features

Feature requests are welcome! Please include:

- **Use case**: Why is this feature needed?
- **Proposed solution**: How should it work?
- **Alternatives considered**: Other approaches you thought of

### 🔧 Code Contributions

1. Look for issues labeled `good first issue` or `help wanted`
2. Comment on the issue to let others know you're working on it
3. Fork and create a branch
4. Make your changes
5. Submit a PR

---

## 🛠️ Development Setup

```bash
# Clone your fork
git clone https://github.com/jayachandranpm/python-code-visualizer.git
cd python-code-visualizer

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Run tests
python test_audit.py
```

---

## 🔀 Pull Request Process

1. **Update documentation** for any changed functionality
2. **Add tests** for new features
3. **Follow the style guide** (see below)
4. **One feature per PR** - keep changes focused
5. **Write clear commit messages**

### PR Checklist

- [ ] Code follows project style guidelines
- [ ] Tests pass locally
- [ ] Documentation updated
- [ ] Commit messages are clear

---

## 🎨 Style Guidelines

### Python

- Follow [PEP 8](https://pep8.org/)
- Use type hints where appropriate
- Write docstrings for public functions
- Keep functions focused and small

### HTML/CSS/JavaScript

- Use 4-space indentation
- Prefer CSS variables for colors
- Keep JavaScript modular

### Commit Messages

```
<type>: <short description>

<optional longer description>
```

Types: `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`

Example:
```
feat: add variable filtering in debug panel

Adds a search input to filter variables by name.
Helps when debugging code with many local variables.
```

---

## 🏷️ Issue Labels

| Label | Description |
|-------|-------------|
| `bug` | Something isn't working |
| `enhancement` | New feature request |
| `good first issue` | Good for newcomers |
| `help wanted` | Extra attention needed |
| `documentation` | Documentation improvements |

---

## ❓ Questions?

Feel free to open an issue with the `question` label!

---

Thank you for contributing! 🙌
