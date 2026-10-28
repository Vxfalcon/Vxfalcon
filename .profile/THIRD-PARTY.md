Profile cards are generated with [Expressive Profile](https://github.com/metawka/expressive-profile), by metawka (MIT). The upstream action is pinned to the same revision used to generate the initial cards. Its license is retained here.

The SVG cards embed Google Sans Flex / Roboto Flex font data (SIL Open Font License); licenses are retained here. Material Symbols uses Apache 2.0, and Simple Icons uses CC0 1.0. Brand icons belong to their respective owners.

Edit `profile.json` to change the style or content. The daily-refresh workflow is prepared in `.profile/expressive-profile.yml`. It is not active: the connected CLI login lacks the `workflow` scope needed to publish `.github/workflows/expressive-profile.yml`. To enable it, add that template at the workflow path through an authorized GitHub session. `PROJECTS.md` preserves the detailed project write-ups and is not generated or overwritten by the action.
