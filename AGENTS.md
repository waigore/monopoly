# AGENTS.md

Instructions for coding agents working in this repository. Human contributors should follow [CONTRIBUTING.md](CONTRIBUTING.md).

## Project

`monopoly` is a simple cross-platform clone of the property-trading board game. It is licensed under the Apache License 2.0 (`LICENSE`).

The tree currently holds the license and these docs. There is no application code, package manifest, or task runner yet. Record real commands here when they appear. Leave this file accurate.

## Defaults

- Make the smallest change that completes the request.
- Read the files you will change and match the style already in the tree.
- Ask before choosing a language, framework, engine, or directory layout. None is selected yet.
- Ask before adding a dependency, package manager, lockfile, or CI workflow.
- Ask before deleting files, rewriting history, force-pushing, or editing `LICENSE`.
- State what you ran and what the result was. If a check does not exist, say so.
- Keep rules logic deterministic and independent of any user interface, so the same game can run on more than one platform.

## Commands

No install, lint, test, or run command exists yet.

When a manifest or workflow lands, copy the exact commands into this section, including flags. Until then, do not install packages or generate a project skeleton unless the user asked for that setup.

## Layout

```text
LICENSE                 Apache License 2.0
AGENTS.md               Instructions for coding agents
CONTRIBUTING.md         Instructions for human contributors
docs/workflow/          Processes for landing changes
```

Put new source in a directory the project already uses. If none exists, ask where it should live before creating a tree of folders.

## Game

Implement the familiar property-trading game: a board of streets, railroads, and utilities; buying and rent; houses and hotels; Chance and Community Chest; jail; auctions; trading; and bankruptcy.

- House rules (free parking, custom auctions, and similar) wait for an explicit option.
- Multiplayer accounts and networking wait until a task asks for them.
- Name types and functions for the game concept they represent.

## Assets and trademarks

This is an independent project. Monopoly and its official board, cards, tokens, and art belong to their owner.

- Create original names, colors, text, and artwork, or use material with a clear license that allows this use.
- Keep third-party asset licenses in the repo next to the asset or in a credits file.
- Leave official logos and endorsement language out of the product, docs, and repo metadata.

## Code style

Follow the formatter and linter checked into the repo once they exist. Until then:

- Prefer straightforward code over an abstraction with a single caller.
- Comments explain rules and constraints. They should earn their place.
- New source files carry the Apache-2.0 header from the appendix of `LICENSE`, with the year and the copyright holder's name filled in. Use the comment syntax of that file type.

## Git

Read `docs/workflow/` for the process that gets changes onto `main`.

- The default branch is `main`. Branch from it as `type/short-topic`, for example `feat/board-model`.
- Use [Conventional Commits](https://www.conventionalcommits.org/): `feat:`, `fix:`, `docs:`, `test:`, `refactor:`, `chore:`.
- Write an imperative subject with no trailing period, ideally under 72 characters.
- Keep each commit to one logical change.
- Leave secrets, credentials, large generated binaries, and local editor state uncommitted.

## Finish

Report what changed, why, how you checked it, and any check you could not run.
