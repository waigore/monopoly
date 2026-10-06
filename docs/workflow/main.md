# Getting changes into main

`main` accepts changes only through a squash-merged pull request.

1. Branch from `main`.
2. Open a pull request into `main`.
3. The `trigger-automerge` check must pass, and the branch must be up to date with `main`.
4. Squash-merge. GitHub deletes the head branch after the merge.

Pushes straight to `main`, including force-pushes, are rejected. A review is not required. A commit that GitHub cannot attribute to an account needs one approving review.

After `trigger-automerge` succeeds, the `enable-automerge` workflow squash-merges the pull request if it is not a draft, targets `main`, and is up to date. It does not use GitHub auto-merge: this job is a non-required check, which puts the PR in `UNSTABLE` status, and GitHub will not arm auto-merge in that state.
