# Conventions

## GitHub

If you are reading this file, it is likely that you know we are using GitHub as our version control. There are some conventions and practices that we as a group use to keep our GitHub space clean.

### Repository naming

Use concise and descriptive names. Please use hyphens instead of spaces when naming a new repository. Every repository should be always lower case.

Examples:

- `developer-docs`
- `module-development-kit`

#### Codenames

Codenames that are not descriptive have to be accepted by a `Maintainer` first.

### Branch naming

Main branches are always called `main`. Please make sure you always keep that as your default branch for the repository.

We use a branch naming strategy where the branch name begins with the type of the branch, then a slash followed by the brief description of the branch where words are separated with hyphens: `<type>/brief-description-of-branch`. The branch name should be all lowercase characters. Please avoid long git branchnames.

The current accepted types are:

- `feat`: New feature added to the project
- `fix`: Fix of a bug or issue
- `docs`: Addition or change of documentation
- `exp`: Experiments
- `devops`: Change in devops

### Commits

Commits should follow the known [Conventional commits](https://www.conventionalcommits.org/) convention. To ensure that your commit message follows the convention, please check it with [commitlint](https://commitlint.js.org/).

#### Types and their meanings

- `feat`: A new feature
- `fix`: A bug fix
- `chore`: Routine tasks (e.g., updating dependencies)
- `docs`: Documentation changes
- `style`: Code style changes (formatting, missing semi-colons, etc.)
- `refactor`: Code changes that neither fix a bug nor add a feature
- `test`: Adding or updating tests
- `perf`: Performance improvements
- `ci`: Changes to CI configuration files and scripts

#### Scopes

Scopes are used for specific parts/submodules of the codebase. In the case of this repository, a scope is the specific Markdown file that is being updated. Note: we are using mostly the `docs` type to describe changes in this repository.

A scope might be a single file in small codebases, but usually it is a separate submodule. In the kernel repository, `vmm` or `acpi` would be a scope.

### Merging

We use GitHub's rebase. Please ensure that each branch is only merged once this way. After merge, the branch should be deleted. This way we can keep our linear history clean. If you have trouble with rebasing, please let us know.

## Special files

- Every single repository should have a `README.md` in its root.

## Linting

### Markdown

Please use the `markdownlint_cli2` linting engine or any linting tool built on it to ensure consistency in Markdown files. Using the default setting should suffice.

### Rust

Please ensure that you are using our special `Clippy` configuration made to automatically follow some of our Rust conventions.

### Bashscripts

Bashscript is not really a cross-platform solution. Don't use it if you don't have to. If it does make sense to use a bashscript, please make sure it doesn't have bashism and is POSIX compatible. You can use [ShellCheck](https://www.shellcheck.net/) to verify these properties.
