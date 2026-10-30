## 2026-06-25 - Module-scope Regex Compilation in Sanitization Utilities
**Learning:** Dynamic compilation of regular expressions and array mapping inside hot-path text sanitizers (e.g. `sanitizeErrorMessage`, `sanitizeThoughtContent`, `sanitizeToolArgs`) causes heavy heap allocations and CPU overhead on streaming output.
**Action:** Always hoist static RegExp definitions and normalized pattern lists to module scope when the pattern input list (`SENSITIVE_KEY_PATTERNS`) is static.
