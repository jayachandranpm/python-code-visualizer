# 🚀 Publishing Guide

This guide covers how to publish **Python Code Visualizer** to GitHub and PyPI.

---

## 📦 Part 1: Publish to GitHub

### Step 1: Create a GitHub Repository

1. Go to [github.com/new](https://github.com/new)
2. Repository name: `python-code-visualizer`
3. Description: "An interactive step-by-step Python code execution visualizer"
4. Set to **Public**
5. **Don't** initialize with README (we already have one)
6. Click "Create repository"

### Step 2: Initialize Git and Push

```bash
# Navigate to your project
cd "/Users/jaya-20646/Python Visualilzer"

# Initialize git
git init

# Add all files
git add .

# Create initial commit
git commit -m "🎉 Initial release: Python Code Visualizer v1.0.0"

# Rename branch to main
git branch -M main

# Add remote (replace YOUR_USERNAME)
git remote add origin https://github.com/YOUR_USERNAME/python-code-visualizer.git

# Push to GitHub
git push -u origin main
```

### Step 3: Create a Release

1. Go to your repo → "Releases" → "Create a new release"
2. Tag: `v1.0.0`
3. Title: `v1.0.0 - Initial Release`
4. Description: Copy from below
5. Click "Publish release"

**Release Notes Template:**
```markdown
## 🎉 Python Code Visualizer v1.0.0

First public release!

### Features
- 📍 Line-by-line code execution tracing
- 📊 Variable state visualization
- 🔥 Execution heatmap (hot loops)
- 📚 Call stack visualization
- ⚠️ Exception handling display
- 💬 Input() mocking support
- ⏱️ Timeline with event markers
- ⌨️ Keyboard navigation
- 🛡️ Timeout and step limit protection

### Installation
```bash
pip install python-code-visualizer
```
```

---

## 📤 Part 2: Publish to PyPI

### Prerequisites

1. **Create a PyPI Account**
   - Go to [pypi.org/account/register](https://pypi.org/account/register/)
   - Verify your email

2. **Create API Token**
   - Go to [pypi.org/manage/account/token](https://pypi.org/manage/account/token/)
   - Create token with "Entire account" scope
   - **Save this token securely!**

3. **Install Build Tools**
   ```bash
   pip install build twine
   ```

### Step 1: Update Package Info

Edit `pyproject.toml`:
- Replace `Your Name` with your actual name
- Replace `your.email@example.com` with your email
- Replace `Your Name` with your actual name

### Step 2: Build the Package

```bash
cd "/Users/jaya-20646/Python Visualilzer"

# Clean previous builds
rm -rf dist/ build/ *.egg-info

# Build the package
python -m build
```

This creates:
- `dist/python_code_visualizer-1.0.0.tar.gz` (source)
- `dist/python_code_visualizer-1.0.0-py3-none-any.whl` (wheel)

### Step 3: Test on TestPyPI (Recommended)

```bash
# Upload to TestPyPI first
python -m twine upload --repository testpypi dist/*

# When prompted:
# Username: __token__
# Password: <your-testpypi-token>

# Test installation
pip install --index-url https://test.pypi.org/simple/ python-code-visualizer
```

### Step 4: Upload to PyPI (Production)

```bash
# Upload to real PyPI
python -m twine upload dist/*

# When prompted:
# Username: __token__
# Password: <your-pypi-token>
```

### Step 5: Verify Installation

```bash
# Install from PyPI
pip install python-code-visualizer

# Test it works
python -c "from PythonVisualizer import CodeVisualizer; print('Success!')"
```

---

## 🔄 Updating the Package

### For future releases:

1. **Update version** in `pyproject.toml`
2. **Rebuild**: `python -m build`
3. **Upload**: `python -m twine upload dist/*`
4. **Create GitHub release** with matching tag

---

## 🤖 Automating with GitHub Actions (Optional)

Create `.github/workflows/publish.yml`:

```yaml
name: Publish to PyPI

on:
  release:
    types: [published]

jobs:
  pypi-publish:
    runs-on: ubuntu-latest
    permissions:
      id-token: write
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-python@v5
        with:
          python-version: '3.11'
      - run: pip install build
      - run: python -m build
      - uses: pypa/gh-action-pypi-publish@release/v1
```

This automatically publishes to PyPI when you create a GitHub release!

---

## ✅ Checklist

- [ ] GitHub repo created
- [ ] Code pushed to GitHub
- [ ] Release created on GitHub
- [ ] PyPI account created
- [ ] API token generated
- [ ] Package built successfully
- [ ] Tested on TestPyPI
- [ ] Published to PyPI
- [ ] Installation verified

---

## 🔗 Quick Links

- [PyPI Dashboard](https://pypi.org/manage/projects/)
- [TestPyPI Dashboard](https://test.pypi.org/manage/projects/)
- [GitHub Releases Guide](https://docs.github.com/en/repositories/releasing-projects-on-github)
- [Python Packaging Guide](https://packaging.python.org/tutorials/packaging-projects/)
