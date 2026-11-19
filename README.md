# DaaS prototypes

Two static prototypes built in Claude Design, sharing one design system.

- `admin/index.html`: Admin (team switcher, Insights, Members)
- `consultant/index.html`: Consultant (workspace, canvas, documents, chat)
- `CLAUDE.md`: the design system rules both follow

## Updating
1. Export the latest HTML from each artifact (download option).
2. Replace `admin/index.html` or `consultant/index.html` with it.
3. Commit. Vercel redeploys automatically.

## Vercel setup
Two projects from this one repo:
- Root Directory `admin`, framework "Other", no build command.
- Root Directory `consultant`, framework "Other", no build command.
