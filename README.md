# Static Code Analysis – Inventory System

---

## 📌 Introduction
This project focuses on performing static code analysis on a Python-based Inventory System.  
The aim is to identify and correct coding issues related to:

- Code quality
- Security vulnerabilities
- Python PEP 8 style compliance
- Error handling and robustness

The original code had several hidden issues that were discovered using automated static analysis tools.

---

## 🛠️ Tools Used

| Tool | Purpose |
|------|---------|
| **Pylint** | Code quality issues (naming, docstrings, logic flaws) |
| **Flake8** | Enforcing PEP 8 style and formatting rules |
| **Bandit** | Detecting Python security vulnerabilities |

Each tool contributed to identifying different types of issues, ensuring comprehensive improvement.

---

## ❌ Issues Identified
Key categories of issues detected included:

- Missing module and function docstrings
- Non-PEP8 naming conventions (e.g., `addItem`)
- Mutable default arguments (`logs=[]`)
- Bare exception handling that hides real errors
- Use of `eval()` — a high-risk security vulnerability
- Unsafe file handling without context managers
- Lack of input validation for item names and quantities
- Formatting problems like line length and blank lines

---

## ✅ Fixes Implemented
After analysis, the following fixes were applied:

- Added input validation and meaningful exceptions
- Removed insecure usage of `eval()`
- Replaced bare `except:` with specific exceptions like `KeyError`
- Added full documentation (module + functions)
- Updated file operations to use `with open(..., encoding="utf-8")`
- Reformatted code according to PEP 8 standards (line length, spacing, blank lines)
- Removed unused imports and corrected dictionary iterations
- Ensured the program continues execution even when errors occur, showing clear messages

---

## 🔄 Behavioral Improvements

| Before Fix | After Fix |
|-----------|-----------|
| Code stopped after first error | Every step executes; errors reported individually |
| Silent failures | All issues clearly shown to the user |
| Security vulnerability from `eval()` | Fully removed |
| Invalid data accepted | Strict validation prevents corruption |

The final code is secure, robust, and much easier to maintain.

---

## 🎯 Conclusion
Static analysis significantly improved the code by:

- Preventing security threats
- Improving code readability and maintainability
- Ensuring proper standards and best practices
- Making debugging much easier

These tools are essential in real-world development for ensuring safe and reliable applications.

---
