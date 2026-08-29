# Links registry

Now that everything lives in one repo, almost every internal link is a relative path and needs no maintenance. This file tracks the handful that still hardcode `VemTech6/cyberx-collective` and will need a find-and-replace if this repo is ever renamed, transferred to an org, or made public under a different slug.

## Absolute URLs used in this repo

| File | Link | Why it's absolute |
|---|---|---|
| `README.md` | `https://github.com/VemTech6/cyberx-collective/issues` | GitHub's Issues tab isn't reachable via a relative file path |
| `opportunities/README.md` | `https://github.com/VemTech6/cyberx-collective/issues` | Same reason |

## Not tracked here

- Relative links (`start-here/README.md`, `../assets/...`, etc.) — these survive a rename/transfer automatically.
- External links (Instagram, learning platforms, federal program pages) — unaffected by anything happening to this repo.

## If this repo goes public later

Nothing here needs to change for that — visibility and URLs are independent. Just flip Settings → General → Danger Zone → Change visibility.

## If this repo transfers to an org or gets renamed

1. Find-and-replace `VemTech6/cyberx-collective` with the new `owner/repo` in the two files above.
2. Re-check branch protection carried over (GitHub usually preserves rulesets on transfer, but verify).
3. Re-pin the repo wherever it was pinned (pinning doesn't survive a transfer automatically).
