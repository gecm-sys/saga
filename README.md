# Ladies of Hive bot

Upvotes and comments on posts in the Ladies of Hive community (hive-124452).

## Setup
1. New GitHub repo, upload these files.
2. Generate a state key:
   `python -c "from cryptography.fernet import Fernet; print(Fernet.generate_key().decode())"`
3. Repo Settings > Secrets and variables > Actions:
   - Secrets: `HIVE_POSTING_KEY`, `GEMINI_API_KEY`, `STATE_KEY`
     (optional: `COMMENT_RULES`, `BLACKLIST`, `GENERIC_PHRASES`, `EXTRA_SKIP_HINTS`, `EMOJIS`)
   - Variables: `HIVE_ACCOUNT`, `MIN_HP` (5000), `DRY_RUN` (`true` first, then `false`)
4. Run the `sync` workflow manually in dry-run mode, check the log, then set `DRY_RUN=false`.

## New variables
| Name | Default | Meaning |
| --- | --- | --- |
| `COMMUNITY` | `hive-124452` | community to work on |
| `SORT` | `trending` | `trending`, `hot` or `created` |
| `MAX_AGE_HOURS` | `48` | ignore posts older than this |
| `MIN_HP` | `5000` | minimum effective HP of the author |
| `EMOJI_CHANCE` | `0.4` | chance (0-1) that a comment ends with a flower emoji |
| `EMOJIS` (secret) | flowers | comma separated list to replace the flower set |
