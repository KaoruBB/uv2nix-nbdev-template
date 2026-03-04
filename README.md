# uv2nix-nbdev-template

A minimal template for [nbdev](https://nbdev.fast.ai/) projects using [uv2nix](https://github.com/adisbladis/uv2nix) and Nix flakes.

## Features

- **nbdev3 Support**: Fully compliant with the Jan 2026 major update (no `settings.ini`, all configurations in `pyproject.toml`).
- **uv2nix integration**: Fast and reproducible dependency management using `uv`.
- **Nix flake**: Deterministic development environment and build.
- **src-layout**: Modern Python project structure.

## Getting Started

### Prerequisites

- [Nix](https://nixos.org/download.html) with flakes enabled
- [direnv](https://direnv.net/) (recommended)

### Creating a New Project

1. Click the "Use this template" button at the top of this repository page.
2. Clone your new repository.
3. **Important**: Update the project details in `pyproject.toml` (especially `name`, `authors`, and `[tool.nbdev]` settings).

### Development Workflow

```bash
# After cloning your new repository
cd your-project-name

# If using direnv:
direnv allow

# Add new Python dependencies
uv add <package-name>
# Sync Nix environment
direnv reload


# Edit your notebooks in nbs/ directory...

# Export notebooks to library (src/uv2nix_nbdev_template/)
nbdev-export

```

## nbdev3 Compatibility (Jan 2026 Update)

This template follows the latest `nbdev` standards. It uses `pyproject.toml` for all configurations, including `nbdev` specific settings under `[tool.nbdev]`. This eliminates the need for a separate `settings.ini` file.

## Project Structure

- `flake.nix`: Nix flake configuration.
- `pyproject.toml`: Python project dependencies and `nbdev` settings.
- `nbs/`: Jupyter notebooks for development and documentation.
- `src/`: Exported Python library (automatically managed by `nbdev-export`).
- `uv.lock`: Lock file for Python dependencies.
- `.envrc`: direnv configuration.

## License

MIT
