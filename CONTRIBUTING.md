# Contributing

Thanks for helping with `monopoly`, a simple cross-platform property-trading game. The project is licensed under the Apache License 2.0. See [LICENSE](LICENSE).

Coding agents should also follow [AGENTS.md](AGENTS.md).

## Current state

The repository is just getting started. It contains the license and contributor docs. There is no application code and no documented install, lint, or test command yet.

For the first implementation, open an issue and agree the language and platform before writing a large patch. Small docs fixes can go straight to a pull request.

## Ways to help

- Report a bug or a question about the rules.
- Improve documentation.
- Add code once a stack is chosen.
- Contribute original art, audio, or board text.

## Issues

Include:

- What you expected and what happened.
- Steps to reproduce, or the rules question you want answered.
- Platform and version, when a build exists.

Search open issues before opening a new one.

## Changes

1. Fork the repository and branch from `main`. Name the branch `type/short-topic`, for example `docs/setup` or `feat/board-model`.
2. Keep the change focused on one thing.
3. Open a pull request against `main`.

New source files should include the Apache header from the appendix of `LICENSE`, with the year and copyright holder filled in.

## Development

No setup or test command exists yet. When one is added, it will be listed here and in `AGENTS.md`. Use that command and describe the result in the pull request.

When code exists:

- Add or update tests for the behavior you change.
- Keep game rules independent of the user interface.
- Run the project's test and lint commands before asking for review.

## Commit messages

Use [Conventional Commits](https://www.conventionalcommits.org/):

```text
feat: add the street rent table
fix: resolve mortgage interest on bankrupt sale
docs: describe the local test command
```

Write the subject in the imperative mood, with no trailing period.

## Pull requests

- Use a conventional commit subject as the title.
- Explain what changed and why.
- Say how you tested, including commands you could not run because they do not exist yet.
- Include a screenshot or clip for visible UI changes.
- Link related issues.

A maintainer will review and merge. Update the branch if the review asks for changes.

## Assets

Submit original work, or work whose license allows use in this project. Include the license and attribution for anything you did not create. Official Monopoly board art, card text, tokens, fonts, and audio are not accepted.

## License of contributions

By submitting a contribution, you agree that it is licensed under the Apache License 2.0, the same terms as the rest of the repository.
