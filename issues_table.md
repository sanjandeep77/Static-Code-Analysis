# Static Code Analysis — Issues & Fixes (Based on Provided Reports)

| Source | Code(s) | Where | Issue | Fix / Rationale | Status |
|---|---|---|---|---|---|
| Pylint | **C0114** | module | Missing module docstring | Added concise module docstring | ✅ Fixed |
| Pylint | **C0116** | functions | Missing function docstrings | Added short docstrings for each function | ✅ Fixed |
| Pylint | **C0103** | addItem/removeItem/getQty/loadData/saveData/printData/checkLowItems | Non-snake_case function names | Kept names to preserve `main()`; suppressed with `# pylint: disable=invalid-name` | ☑ Addressed |
| Pylint | **W0102** | addItem | Mutable default `logs=[]` | Switched to `logs=None`, init inside | ✅ Fixed |
| Pylint | **W0702** / Flake8 **E722** | removeItem | Bare `except` | Use explicit `KeyError`; no silent pass | ✅ Fixed |
| Pylint | **C0206** | printData, checkLowItems | Iterating dict without `.items()` | Use `.items()` and comprehensions | ✅ Fixed |
| Pylint | **W0108** | main | Unnecessary lambdas | Replaced with `functools.partial` + small helpers | ✅ Fixed |
| Pylint | **W0718** | wrapper | Broad `except Exception` | Catch specific exceptions in loop | ✅ Fixed |
| Flake8 | **F401** | imports | Unused imports | Removed unused; keep only required imports | ✅ Fixed |
| Flake8 | **E302/E305** | file-wide | Missing blank lines around defs | Formatted per PEP 8 | ✅ Fixed |
| Flake8 | **E501** | a few lines | Lines >79 chars | Wrapped strings across multiple lines | ✅ Fixed |
| Bandit | **B110** | removeItem (original) | `try/except/pass` | Now raise real errors; handled per-op in runner | ✅ Fixed |
| Bandit | **B307** | main (original) | `eval()` usage | Removed; added safe placeholder print | ✅ Fixed |
| Runtime | — | main | Invalid inputs (`-2`, non-int qty), missing item | Validation raises; per-op try/except prints error, continues | ✅ Fixed |