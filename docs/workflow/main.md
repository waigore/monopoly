# Getting changes into main

`main` accepts changes only through a squash-merged pull request.

1. Branch from `main`.
2. Open a pull request into `main`.
3. The `trigger-automerge` check must pass, and the branch must be up to date with `main`.
4. Squash-merge. GitHub deletes the head branch after the merge.

Pushes straight to `main`, including force-pushes, are rejected. A review is not required. A commit that GitHub cannot attribute to an account needs one approving review.

Auto-merge is enabled automatically by the `enable-automerge` workflow on non-draft pull requests into `main`. Enable it manually only if that job has not run yet and `trigger-automerge` is still pending. The pull request merges when that check passes and the branch is up to date.
