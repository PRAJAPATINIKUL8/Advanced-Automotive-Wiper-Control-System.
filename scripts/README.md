# update_project_data.sh

This folder contains a helper script `update_project_data.sh` which:

- Optionally sets Git `user.name` and `user.email` (locally for the repo or globally).
- Syncs files from a source folder into the repository using `rsync`.
- Stages and commits any changes if present.

Usage examples

1. Set local repo git user and sync (recommended):

```bash
./scripts/update_project_data.sh --name "Your Name" --email "you@example.com" --src /path/to/source --dest /path/to/repo
```

2. Set git user globally and do a dry-run of the sync:

```bash
./scripts/update_project_data.sh --global --dry-run --name "Your Name" --email "you@example.com" --src /path/to/source --dest /path/to/repo
```

Notes about VS Code and Git user settings

- VS Code uses the Git installation on your machine. If you set the git user via `git config --global` it will be used everywhere (including from VS Code).
- To set Git user in VS Code UI: open Command Palette (Cmd+Shift+P) → Preferences: Open Settings (UI) → search for `git`. For user.name/email you still need to use `git config` as the UI doesn't expose these fields; alternatively, set them in the repository settings by running the script above.
- If you prefer to keep repo settings local (recommended for shared machines), omit `--global`.

Safety and exclusions

- The script excludes `.git`, `node_modules`, `.vs` and `*.log` by default. Adjust `RSYNC_EXCLUDES` in the script if you need different behavior.
- The script will `git init` the destination folder if it doesn't contain a `.git` directory.

Problems or customizations

- Want the script to prompt for values interactively? I can add that.
- Want different exclude patterns or a different commit message format? I can update it.
