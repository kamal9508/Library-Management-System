
# Library Management System (Python)

A simple, testable Library Management System that showcases **two data structure backends**:
1. **Array-based** (Python `list`)
2. **Custom Singly Linked List**

Pick your storage at runtime via CLI flag.

---

## Features

- Add/list/search **Books** and **Members**
- **Borrow/Return** flow with basic checks
- Two pluggable storage backends (Array and Linked List)
- Clean service layer and models
- CLI app using `argparse`
- Unit tests with `pytest`

---

## Quick Start

```bash
# 1) Create and activate a venv (recommended)
python -m venv .venv
# Windows: .venv\Scripts\activate
# Unix/Mac: source .venv/bin/activate

# 2) Install dev dependency (pytest)
pip install -r requirements.txt

# 3) Run the CLI (defaults to array backend)
python -m library.cli

# Or use the linked list backend
python -m library.cli --backend linkedlist
```

### CLI Examples

```bash
# Add a member
python -m library.cli --add-member "Alice"

# Add a book
python -m library.cli --add-book "Clean Code" "Robert C. Martin" 2008

# List all books
python -m library.cli --list-books

# Search books by title or author (substring, case-insensitive)
python -m library.cli --search-book clean

# Borrow a book
python -m library.cli --borrow "Alice" "Clean Code"

# Return a book
python -m library.cli --return "Alice" "Clean Code"
```

---

## Project Structure

```
Library-Management-System/
├─ src/
│  └─ library/
│     ├─ __init__.py
│     ├─ models.py
│     ├─ storage.py
│     ├─ array_repo.py
│     ├─ linkedlist_repo.py
│     ├─ service.py
│     └─ cli.py
├─ tests/
│  └─ test_service.py
├─ requirements.txt
├─ pyproject.toml
└─ LICENSE
```

---

## Design Notes

- `storage.py` defines the **StorageProtocol** interface used by the service.
- `array_repo.py` implements storage using Python lists (dynamic arrays).
- `linkedlist_repo.py` implements a simple **singly linked list** with nodes.
- `service.py` is the **business layer** with validations for borrow/return.
- `cli.py` wires it all together and provides a minimal command-line interface.

---

## Running Tests

```bash
pytest -q
```

---

## License

MIT
