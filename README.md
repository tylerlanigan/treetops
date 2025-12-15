# Zephyr

A simple Python package template.

## Installation

Install from PyPI:

```bash
pip install zephyr
```

Or install from source:

```bash
git clone https://github.com/yourusername/zephyr.git
cd zephyr
pip install .
```

## Usage

```python
from zephyr.example import hello

# Greet the world
print(hello())
# Output: Hello, World!

# Greet someone specific
print(hello("Alice"))
# Output: Hello, Alice!
```

## Development

### Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/zephyr.git
   cd zephyr
   ```

2. Install in development mode:
   ```bash
   pip install -e .
   ```

### Running Tests

```bash
pytest tests/
```

### Building the Package

```bash
python -m build
```

This will create distribution files in the `dist/` directory.

## Publishing to PyPI

This package uses GitHub Actions for automated publishing. To publish a new version:

1. Update the version in `pyproject.toml` and `zephyr/__init__.py`
2. Commit your changes:
   ```bash
   git add .
   git commit -m "Release version X.Y.Z"
   ```
3. Create and push a version tag:
   ```bash
   git tag vX.Y.Z
   git push origin vX.Y.Z
   ```

The GitHub Actions workflow will automatically build and publish to PyPI when a tag matching `v*` is pushed.

### Setting Up PyPI Credentials

Before publishing, you need to set up PyPI credentials:

1. Create a PyPI API token:
   - Go to https://pypi.org/manage/account/token/
   - Create a new API token (scope: "Entire account" or project-specific)
   - Copy the token (you won't be able to see it again)

2. Add the token as a GitHub Secret:
   - Go to your repository on GitHub
   - Navigate to Settings → Secrets and variables → Actions
   - Click "New repository secret"
   - Name: `PYPI_API_TOKEN`
   - Value: Paste your PyPI API token
   - Click "Add secret"

3. (Optional) For testing, create a TestPyPI token:
   - Go to https://test.pypi.org/manage/account/token/
   - Create a new API token
   - Add it as `TEST_PYPI_API_TOKEN` GitHub Secret

## License

MIT License - see [LICENSE](LICENSE) file for details.
