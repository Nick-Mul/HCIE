# HCIE UV Environment Setup

## Quick Start

```bash
cd HCIE
uv venv
uv pip install -e .
```

## Manual Steps

If the above doesn't work, follow these steps:

### 1. Install git-lfs (if not already installed)

```bash
brew install git-lfs
cd HCIE
git lfs install
git lfs pull
```

### 2. Create uv virtual environment

```bash
cd HCIE
uv venv
```

### 3. Install dependencies

```bash
uv pip install numpy rdkit scipy tqdm pytest
uv pip install -e .
```

### 4. Fix Data package

The `Data/` directory needs an `__init__.py` for the package to find data files:

```bash
touch HCIE/Data/__init__.py
```

*(This was added during setup - included in the repo)*

## Usage

```bash
cd HCIE
source .venv/bin/activate
python hcie/main.py "<smiles_with_exit_vectors>" -n <name>
```

## Running Tests

```bash
cd HCIE
source .venv/bin/activate
python -m pytest tests/ -v
```

## Notes

- Python 3.12+ is used (minimum requirement is 3.6+)
- The Data files are stored in git LFS (~245MB total)
- 12/13 tests pass (1 pre-existing test issue with exception type)
