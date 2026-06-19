# Project Name

## About This Template

This is a Python project template that combines [**uv**](https://docs.astral.sh/uv/) — a fast Python package installer and resolver — with [**nbdev**](https://nbdev.fast.ai/) — a notebook-driven development framework. It enables you to write and document Python code directly in Jupyter notebooks, which are automatically converted into a Python package with generated documentation.

**Key Features:**
- **Rapid package management** with `uv` for fast dependency resolution and virtual environment management
- **Notebook-based development** with nbdev for literate programming and documentation
- **Automatic code generation** from notebooks to Python modules
- **Built-in documentation** generation from notebook cells
- **Pre-commit hooks** for code quality checks
- **CI/CD workflows** configured for testing and documentation builds

## Setup Instructions

### 1. Clone/Download the Template

```bash
git clone <repository-url>
cd <project-directory>
```

### 2. Edit `pyproject.toml`

Update the project metadata in `pyproject.toml`:
- `name`: Your project name (must match your package directory)
- `description`: A brief description of your project
- `authors`: Author information
- `dependencies`: List your project dependencies
- `version`: Version number (follow [semantic versioning](https://semver.org/))

Example:
```toml
[project]
name = "my-awesome-package"
description = "A brief description"
version = "0.1.0"
authors = [{name = "Your Name", email = "your.email@example.com"}]
dependencies = ["numpy", "pandas"]
```

### 3. Install `uv`

If you don't have `uv` installed, run:

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

For other installation methods, see the [uv installation guide](https://docs.astral.sh/uv/getting-started/installation/).

### 4. Sync Project Dependencies

```bash
uv sync --all-groups
```

This installs all dependencies, development tools, and optional groups.

### 5. Install Quarto (Optional)

For HTML/PDF documentation generation:

```bash
nbdev-install-quarto
```

### 6. Initialize nbdev

```bash
nbdev-new .
```

This creates the nbdev folder structure (`nbs/`, `docs/`, etc.) and initializes the nbdev configuration file.

### 7. Install Pre-commit Hooks

```bash
pre-commit install
```

This sets up automatic code quality checks before each commit.

## Development Workflow

### Writing Code

1. Create Jupyter notebooks in the `nbs/` directory
2. Annotate code cells with nbdev directives (e.g., `#| export` to export functions to your package)
3. Use markdown cells for documentation and explanations

### Building and Testing

- **Generate code**: `nbdev-build` converts notebooks to Python modules in your package directory
- **Run tests**: `nbdev-test` executes all test cells in your notebooks
- **Build documentation**: `nbdev-build-docs` creates HTML documentation from notebooks
- **Clean**: `nbdev-clean` removes generated artifacts

### Development Commands

```bash
# Export code from notebooks
uv run nbdev-build

# Run all tests
uv run nbdev-test

# Build documentation
uv run nbdev-build-docs

# Clean generated files
uv run nbdev-clean
```

## CI/CD

GitHub Actions workflows are pre-configured to:
- Run all tests on push and pull requests
- Build and validate documentation
- Perform code quality checks via pre-commit
- Deploy documentation (optional)

Check the `.github/workflows/` directory to customize these workflows for your needs.

## Resources

- [uv Documentation](https://docs.astral.sh/uv/)
- [nbdev Documentation](https://nbdev.fast.ai/)
- [Jupyter Notebook Guide](https://jupyter.org/try)
- [Python Packaging Guide](https://packaging.python.org/)

## License

See [LICENSE](LICENSE) file for details.
