# Project Name

A project template using `uv` and `nbdev`.

## Setup Instructions

### 1. Clone/Download

```bash
git clone <repository-url>
cd <project-directory>
```

### 2. Edit `pyproject.toml`

Update the project metadata in `pyproject.toml`:
- `name`: Your project name
- `description`: Project description
- `authors`: Author information
- `dependencies`: Add your project dependencies
- `version`: Version number

### 3. Install `uv`

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

Or see [uv installation guide](https://docs.astral.sh/uv/getting-started/installation/).

### 4. Sync All Groups

```bash
uv sync --all-groups
```

### 5. Install Quarto

```bash
nbdev-install-quarto
```

### 6. Create nbdev Structure

```bash
nbdev-new .
```

This will generate the notebook-based development structure and initialize nbdev configuration.

### 7. Install Pre-commit Hooks

```bash
pre-commit install
```

Pre-commit hooks will automatically run checks before each commit.

## Development Workflow

- Write notebooks in the `nbs/` directory
- Generated code goes to the package directory
- Build documentation with `nbdev-build`
- Test with `nbdev-test`

## CI/CD

GitHub Actions workflows are configured for:
- Running tests on push and pull requests
- Building documentation
- Code quality checks

## License

See LICENSE file for details.
