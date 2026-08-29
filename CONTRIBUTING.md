# Contributing to CyberX Collective

These repos are curated by the e-board and designated maintainers. There are exactly two ways a general body member contributes, both described below — anything outside those two is closed without review.

---

## 🔧 Track 1 — Fixes

The low-friction path. Use it for:

- Broken or dead links
- Outdated information — a program that no longer exists, a tool that's been renamed or deprecated
- Typos
- Formatting errors that break rendering

**Process:** open an issue using the **Fix** template. State what's wrong, where it is (file and section), and what it should say instead. A maintainer verifies and pushes the fix directly. You don't need to open a PR for this — an issue is enough, and it's faster for everyone.

> [!TIP]
> These are genuinely valuable, not busywork. A dead link on the front page of a public repo is the single most common way this org looks unmaintained, and members catch them faster than maintainers do.

## 🏗️ Track 2 — Project Contribution

The substantive path — for members who want to build something that lives in the org, not just fix something that's already there.

1. **Open an issue using the Project Proposal template.** Describe what it is, why it belongs in the org rather than a personal repo, what you'll build, and a rough timeline.
2. **A maintainer reviews it** and either approves, requests changes to the scope, or declines with a reason.
3. **If approved,** you're assigned the issue and given write access to a branch (or a dedicated repo, for larger work).
4. **Build it.** Open a PR against `main` when it's ready.
5. **One maintainer review, then merge.** Your commits stay under your name.

> [!IMPORTANT]
> Proposal first, code second. An unsolicited PR for a project that was never proposed will be closed regardless of quality — scope gets decided before work starts, not after.

**What a good proposal looks like** — a few examples, not a limit:

- A hands-on lab writeup for `start-here/` — walking through a specific exercise (e.g. a vulnerable-VM box, a detection-engineering scenario) step by step
- A study guide for a specific certification (e.g. Security+, CySA+) with practice questions
- A script or small tool other members would actually use (a log-parser, a CTF writeup template generator)
- A workshop's materials — slides plus a hands-on exercise for a meeting topic

## 🚫 Everything Else

Unsolicited PRs, rewrites of existing content, and structural changes are closed without review. This isn't gatekeeping for its own sake — these repos are the public face of the org and appear on members' résumés, so what's in them is deliberate. Members who want a larger role should talk to the e-board in person.

---

## 📋 For Maintainers

- **Branch naming:** `fix/<short-description>` for Track 1, `project/<short-name>` for Track 2.
- **Commits:** describe *why*, not just *what* — imperative mood ("add LetsDefend to SOC track," not "updated README").
- **Merging:** one approving review required before merge into `main` (enforced by branch protection).
