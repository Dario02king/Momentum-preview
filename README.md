# Momentum — temporary preview

Built output only, for real-device visual QA of `Momentum-App` branch
`claude/keen-thompson-jevjzb` before it is merged. No source, no history.

- Built from commit `4be4d52` with `--base=/Momentum-preview/`.
- `sw.js` is deliberately **not** published: its precache list is generated
  for the production path and would be wrong here. Without it every load is
  fresh, which is what a visual review wants.
- The sourcemap is omitted for the same reason — it is not needed to look at
  the app.

The files sit at the repository root, so **either** Pages source works:
*Deploy from a branch* (`main`, `/ (root)`) or *GitHub Actions* (re-run the
`Publish preview` workflow).

Delete this repository once the review is done.
