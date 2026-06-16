Deploy rpong to GitHub Pages.

Steps:
1. Run `git status` to see what has changed.
2. Stage all modified tracked files with `git add -u`, plus any new intentional files (never add .DS_Store, secrets, or unrelated files).
3. Ask the user for a commit message if they haven't provided one as an argument; otherwise use the argument directly.
4. Commit with that message.
5. Push to `origin main`.
6. Confirm success and remind the user the live site at https://aaronr.github.io/rpong/ updates within about a minute.
