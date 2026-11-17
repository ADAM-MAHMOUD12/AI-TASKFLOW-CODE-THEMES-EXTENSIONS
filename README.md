# AI TaskFlow Code Themes and Extensions

This folder is the starter content for the public repository
`ADAM-MAHMOUD12/AI-TASKFLOW-CODE-THEMES-EXTENSIONS`. Publish these files at the
repository root so the Theia editor can read `catalog.json` from the `main`
branch.

The editor accepts catalog version 1:

- `themes`: JSON color palettes using only the color keys in the sample theme.
- Theme entries may include `author`, a Markdown `readme` path, and an optional
  `preview` image path (`png`, `jpg`, or `webp`) to credit the creator and show
  theme documentation and screenshots in the store.
- `extensions`: `.vsix` files stored in this repository. Installation executes
  extension code, so the editor asks for confirmation before installing.
- `skills`: `SKILL.md` files stored in this repository. Installation adds
  instructions to the current workspace and asks for confirmation.

Use unique lowercase IDs containing only letters, digits, and hyphens. Asset
paths must remain inside `themes/`, `extensions/`, or `skills/`. Do not add
credentials, access tokens, or executable installers.
