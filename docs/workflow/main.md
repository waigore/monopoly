---
title: Getting changes into main
tags: [docs, workflow, main, merge]
last_edited: 2026-10-07
---

# Getting changes into main

## Quick start

`main` accepts changes only through a squash-merged pull request. Branch from `main`, open a PR, wait for `trigger-automerge` to pass with the branch up to date, then let `enable-automerge` squash-merge (or merge manually if that job has not run).

1. Branch from `main`.
2. Open a pull request into `main`.
3. The `trigger-automerge` check must pass, and the branch must be up to date with `main`.
4. Squash-merge. GitHub deletes the head branch after the merge.

Pushes straight to `main`, including force-pushes, are rejected. A review is not required. A commit that GitHub cannot attribute to an account needs one approving review.

After `trigger-automerge` succeeds, the `enable-automerge` workflow squash-merges the pull request if it is not a draft, targets `main`, and is up to date. It does not use GitHub auto-merge: that job is a non-required check, which puts the PR in `UNSTABLE` status, and GitHub will not arm auto-merge in that state.

Treat `trigger-automerge` as the last gate. Any other Actions job that must pass before merge has to finish before `trigger-automerge` does—typically in the same workflow with `needs:` so `trigger-automerge` runs only after those jobs succeed. Parallel workflows that finish after `trigger-automerge` are too late: merge already started.
