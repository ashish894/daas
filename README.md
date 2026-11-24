# DaaS prototypes

Three static prototypes built in Claude Design, sharing one design system.

- `admin/index.html`: Admin (team switcher, Insights, Members)
- `super-admin/index.html`: Super Admin (Admin plus All members across teams)
- `consultant/index.html`: Consultant (workspace, canvas, documents, chat)
- `CLAUDE.md`: the design system rules all three follow

## Updating
1. Export the latest HTML from each artifact (download option).
2. Replace `admin/index.html`, `super-admin/index.html` or `consultant/index.html` with it.
3. Replace `CLAUDE.md` if the design system changed.
4. Commit. Vercel redeploys automatically.

## Vercel setup
Three projects from this one repo, each with framework "Other" and no build command:
- Root Directory `admin`
- Root Directory `super-admin`
- Root Directory `consultant`
