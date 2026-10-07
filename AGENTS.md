# AGENTS.md

Instructions for coding agents working in this repository. Human contributors should follow [CONTRIBUTING.md](CONTRIBUTING.md).

## Project

`monopoly` is a simple cross-platform clone of the property-trading board game. It is licensed under the Apache License 2.0 (`LICENSE`).

The tree currently holds the license, contributor docs, `docs/`, `specs/`, and the shared agent skills directory. Leave this file accurate.

## Layout

```text
LICENSE                 Apache License 2.0
AGENTS.md               Instructions for coding agents
CONTRIBUTING.md         Instructions for human contributors
.agents/skills/         Agent skill definitions (single source)
.grok/skills            Symlink to .agents/skills for Grok
docs/                   Process and contributor Markdown
  agents/               Coding agent setup and skills
  workflow/             How changes land on main
specs/                  Design and contract Markdown
  game/                 Game design
  ui/                   UI and UX
  tech/                 Tech stack and non-functional requirements
  module/               Modules, contracts, and integration
  test/                 Testing tools and instructions
```

Put new source in a directory the project already uses. If none exists, ask where it should live before creating a tree of folders. Put new specs under `specs/` and new process docs under `docs/` in the folder that matches the subject.

## Markdown

Write Markdown under `specs/` and `docs/`. Follow these conventions:

- Keep each file under 500 lines. Split into linked sub-documents when a file would grow past that.
- Link other docs instead of copying the same content.
- Start each file with YAML frontmatter: `title`, `tags` (for search), and `last_edited` (ISO date `YYYY-MM-DD`). Update `last_edited` when you change the file.
- Put a **Quick start** section immediately after the heading so a reader can act without scanning the whole document.
- Do not include a changelog. Git history is the record of edits.

## Specs

Read [specs/README.md](specs/README.md) for the index. Follow the [Markdown](#markdown) conventions above.

## Docs

Read [docs/README.md](docs/README.md) for the index. Follow the [Markdown](#markdown) conventions above.

## Skills

Define every skill in `.agents/skills/<skill-name>/SKILL.md`, the vendor-neutral source. Vendor directories (`.cursor/`, `.grok/`, `.opencode/`) only refer to that tree. Never put a skill definition or a copy in them. Read [docs/agents/skills.md](docs/agents/skills.md) for how each agent finds the skills.

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
