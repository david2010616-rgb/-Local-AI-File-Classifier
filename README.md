# Local-AI-File-Classifier

A local-first, privacy-focused, open-source file classification and organization project written in Python.

## Project goals

The completed application is intended to:

- run locally on macOS and Windows;
- require no cloud AI API for its core classification workflow;
- classify files using filename, document type, title, body text and safe metadata;
- support confidence-based abstention so uncertain documents can be reviewed instead of force-classified;
- learn from user corrections through explicit retraining;
- keep user documents on the user's own computer;
- preview file moves before applying them and maintain recoverable operation history;
- remain suitable for permissive open-source distribution.

## Current status: Phase 1

Phase 1 intentionally implements only the safe recursive file scanner and package skeleton. It does **not** yet extract document contents, train an ML model, move files, create a GUI, or create a database.

This phased approach keeps each subsystem testable before the next one is added.

## Requirements

- Python 3.11 or 3.12
- macOS or Windows are the primary targets

## Development setup

### macOS / Linux

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install -e ".[dev]"
pytest
ruff check .
```

### Windows PowerShell

```powershell
py -3.11 -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install -e ".[dev]"
pytest
ruff check .
```

## Run the Phase 1 scanner

```bash
file-classifier .
```

or:

```bash
python -m file_classifier.main .
```

Useful options:

```bash
file-classifier --show-errors ~/Documents
file-classifier --include-hidden ~/Documents
file-classifier --version
```

Phase 1 does not modify, rename, delete, or move files.

## Planned architecture

Later phases will add:

1. document extraction;
2. SQLite schema and caching;
3. categories and labeled training examples;
4. TF-IDF feature pipelines;
5. Logistic Regression classification;
6. calibrated confidence / review policy;
7. user correction and retraining;
8. desktop GUI;
9. transactional file-operation journal, preview and undo;
10. macOS/Windows packaging;
11. optional local semantic embeddings.

## Privacy

The core product target is local-only operation: no account requirement, no document upload, no telemetry by default, and no paid AI API requirement.

## License

Apache License 2.0. See `LICENSE`.
