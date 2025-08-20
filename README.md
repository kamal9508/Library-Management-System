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
