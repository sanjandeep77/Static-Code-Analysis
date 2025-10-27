# Reflection

**What I fixed and why (short):**
- Replaced bare `except` with specific exceptions to avoid hiding bugs.
- Removed `eval()` to eliminate a security risk flagged by Bandit.
- Added input validation to prevent invalid states (negative or wrong-typed quantities).
- Used safe file I/O with explicit UTF-8 encoding.
- Documented functions and followed PEP 8 (line length, spacing).
- Kept legacy function names to preserve the `main()` calls; suppressed name warnings explicitly.

**What changed the behavior:**
- The program no longer stops on the first error. Each step is wrapped in a try/except, reports its error, and continues.

**What I learned:**
- Static analysis (Pylint/Flake8) helps enforce readability and consistency.
- Bandit highlights real security pitfalls like `eval()` and silent exception handling.
- Good validation plus precise exceptions make failures obvious and easier to debug.

**How I’d use this in CI:**
- Run `flake8` and `pylint` on every PR; run `bandit` in a security job.
- Fail the build on new High/Medium Bandit issues and on style regressions.