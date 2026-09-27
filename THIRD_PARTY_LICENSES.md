# Third-party licenses

## Phase 1 runtime

Phase 1 intentionally has no third-party runtime dependencies.

## Development-only tools

The development environment uses tools such as `pytest`, `pytest-cov`, and `ruff` through the `dev` optional dependency group in `pyproject.toml`. These are development tools and are not required by the Phase 1 runtime package.

Before any future binary release, this file must be updated to include every redistributed runtime library and any required notices/licenses. In particular, future phases must audit the licenses and redistribution requirements of the chosen GUI toolkit, PDF engine, ML libraries, packaging output, and any optional local embedding model.
