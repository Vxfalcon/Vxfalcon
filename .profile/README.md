# Profile maintenance

- `profile.json` controls the Expressive Profile theme, content and links.
- `PROJECTS.md` preserves the original detailed project write-ups, with Ghastly added.
- The current SVG cards are generated from real GitHub data.
- `expressive-profile.yml` in this folder is the ready-to-use daily refresh workflow. It must be copied to `.github/workflows/expressive-profile.yml` using a GitHub login that can write workflows. The current CLI OAuth login cannot publish that path, so automatic refresh is not enabled yet.
- The workflow uses only the built-in repository token, with no personal access token stored in the repository. Both third-party actions are pinned to commit hashes.
