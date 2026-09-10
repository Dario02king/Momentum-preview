# Momentum — temporary preview

Built output only, for real-device visual QA of `Momentum-App` branch
`claude/momentum-pass-2-geometry-r2qzkd` before it is merged. No source, no
history.

- Built from commit `eea0c19` with `--base=/Momentum-preview/`.
- `sw.js` is deliberately **not** published: its precache list is generated
  for the production path and would be wrong here. Without it every load is
  fresh, which is what a visual review wants.
- The sourcemap is omitted for the same reason — it is not needed to look at
  the app.

`index.html` is **the preview repository's own**, not the one the build
emits: it carries `apple-mobile-web-app-status-bar-style: black-translucent`,
which is the only style under which the web view reaches the physical top
edge and `env(safe-area-inset-top)` becomes a real value. That fix lives here
and has never been in `Momentum-App`, whose `index.html` still says
`default`. Only the two asset URLs are rewritten on each publish, so a
rebuild cannot quietly undo it — and the preview shows the safe-area
behaviour a real device actually has.

The files sit at the repository root, so **either** Pages source works:
*Deploy from a branch* (`main`, `/ (root)`) or *GitHub Actions* (re-run the
`Publish preview` workflow).

Delete this repository once the review is done.
