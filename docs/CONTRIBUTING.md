# 🤝 Contributing Guidelines

<!-- #region summary -->
If you encounter any problems with the script, feel free to [create an issue](https://github.com/twocaretcat/komodo/issues).

Pull requests, bug reports, translations, and other kinds of contributions are welcome.
<!-- #endregion summary -->

## Finding Issues to Work On

Issues with the `🚦 ready` label are ready to be worked on. If you comment on an issue, I can assign it to you.

Issues with the `🚦 needs triage` label generally need some more information before they can be worked on, but if you
**start a discussion** about it or leave a comment on the issue, I can likely get it ready for you.

If an issue is unclear or you have any questions about how a feature should be implemented, reach out before making any
changes so we can discuss the best way to do it.

## Guidelines

The [Conventional Commits](https://www.conventionalcommits.org/) specification is used for commit messages. [SemVer](https://semver.org/) is used for versioning.

## Tech Stack

This project is written in [TypeScript](https://www.typescriptlang.org/) and uses [Vite](https://vite.dev/) and [vite-plugin-monkey](https://github.com/lisonge/vite-plugin-monkey) to bundle the code into a single file that can be installed as a userscript.

We use [Bun](https://bun.sh/) for package management. You can use another package manager if you want, but you'll have to replace refererences to `bun` or `bunx` in the following places:

- Script commands in `package.json`
- Husky hooks in `.husky/*`
- Workflows in `.github/workflows/*`

Commit conventions are enforced using [Commitlint](https://commitlint.js.org/) via [Husky](https://typicode.github.io/husky/) pre-commit hooks. [Commitizen](https://commitizen-tools.github.io/commitizen/) is set up as well, so you can use `bun commit` to commit changes using an interactive prompt instead of `git commit` if you wish.

[Biome](https://biomejs.dev/) is used for linting and formatting.

[Semantic Release](https://semantic-release.gitbook.io/semantic-release/) is used to automate the release process.

[Vitepress](https://vitepress.dev/) is used to build the documentation site at [komodo.johng.io](https://komodo.johng.io).

## Local Development

Here are some useful commands for working on the project locally.

### Installation

To work on the project locally, first clone the repository and run `bun install` to install the dependencies.

### Building

Vite is used to build both the docs and the script itself, but they are built separately.

#### Script

| Task | Command | Description |
| --- | --- | --- |
| Build | `bun run build` | Build the script and save the output to `dist/`. |
| Preview | `bun preview` | Start a server to test the script locally. |
| Develop | `bun dev` | Start a development server that will rebuild the script automatically when there are changes. |

#### Docs

| Task | Command | Description |
| --- | --- | --- |
| Build Docs | `bun docs:build` | Build the documentation site and save the output to `docs/.vitepress/dist/`. |
| Preview Docs | `bun docs:preview` | Start a server to view the documentation site locally. |
| Develop Docs | `bun docs:dev` | Start a development server that will rebuild the site automatically when there are changes. |

### Linting / Formatting

| Task | Command | Description |
| --- | --- | --- |
| Format | `bun format` | Format the codebase using Biome. |
| Lint | `bun lint` | Lint the codebase using Biome. |
| Commit | `bun commit` | Use an interactive prompt to commit changes with Commitizen. |

### Hooks

| Task | Description |
| --- | --- |
| Prepare | Install Git hooks using Husky when the package is installed. |
| Post Version | Build the script and save the output to `dist/` when the version is updated. |

## License

By contributing to this project, you agree that your contributions will be licensed under the project license.
