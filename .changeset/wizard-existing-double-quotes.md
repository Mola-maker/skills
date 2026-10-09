---
"mattpocock-skills": patch
---

`wizard` template fix: `_existing` now undoes double-quoted `.env` values as well as `write_env`'s single-quoted form, so pressing Enter to keep a current value like `API_KEY="dummy-value"` no longer stores the quotes as part of the credential (#1220). The two decodings are exclusive branches, so a value that really contains double quotes still reads back intact, and a double-quoted value holding escapes, a `$` or an inner quote fails safe so the wizard asks again instead of guessing.
