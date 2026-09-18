# Amazon Codex Skills

Amazon operations skills for Codex. The initial snapshot contains 81 user skills in `agents-skills/` and 4 user skills in `codex-skills/`.

## Install on another Windows computer

1. Install Codex. Inspect any existing skills with the same names and keep a backup before replacing local changes.
2. Copy each directory inside `agents-skills/` to `%USERPROFILE%\.agents\skills\` and each directory inside `codex-skills/` to `%USERPROFILE%\.codex\skills\`. Do not add an extra parent directory.
3. Install required tools separately, especially `lark-cli`, and authorize Feishu as the intended **user** on that computer. Never copy credentials from another computer.
4. Restart Codex if the updated skills do not appear. Check `amazon-listing-development-workflow`, `amazon-negative-keyword-batch-review`, `amazon-auto-router`, `lark-drive`, `lark-doc`, and `lark-sheets` with a read-only task first.

Feishu's current `AMAZON-OPS-ENTERPRISE-HUB` directory is authoritative for business files. Some skill references mention a local `E:\AMAZON-OPS-ENTERPRISE-HUB` path from the source computer; treat such paths as historical pointers and verify the current Feishu resource before use.

## Repository boundary

`Claude-to-IM` is intentionally excluded. The source computer's `_Collections` shortcut catalog, Codex system skills, plugin caches, local collaboration records, tokens, secrets, `.env` files, SQLite data, logs, and reports are also excluded. Some product-specific skill references contain Feishu document links and operating context; access to those documents still depends on Feishu permissions. Review changes for credentials and machine-specific paths before pushing.
