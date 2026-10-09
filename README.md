# .github

Community health files and AI agent instructions for all DDEV repositories.

## Community Health Files

GitHub automatically uses these files as defaults for any DDEV repository that doesn't have its own version:

- `CONTRIBUTING.md` - Contribution guidelines
- `CODE_OF_CONDUCT.md` - Code of conduct
- `FUNDING.yml` - Sponsor button
- `ISSUE_TEMPLATE/` - Issue templates
- `PULL_REQUEST_TEMPLATE.md` - PR template
- `SUPPORT.md` - Support information

`profile/README.md` is the public profile shown at [github.com/ddev](https://github.com/ddev).

For more information, see [GitHub's community health documentation](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file).

## AI Agent Instructions

[`AGENTS.md`](AGENTS.md) holds the organization-wide instructions for AI agents. It is not a community health file, so each repository adds its own `AGENTS.md` with project-specific guidance and a link to this one:

```markdown
# AGENTS.md

Guidance for AI agents working on [PROJECT_NAME].

[Brief description of the project.]

DDEV's [organization-wide patterns](https://raw.githubusercontent.com/ddev/.github/main/AGENTS.md)
cover writing style, git workflow, and PRs; this file wins where they differ.

## Commands

[Build, test, and lint commands.]

## Architecture

[Only the parts that are not obvious from the tree.]
```

Keep shared patterns (writing style, branch naming, commits, PRs) here, and keep project-specific content (commands, testing, architecture) in each repository.

Examples:

- [ddev/ddev](https://github.com/ddev/ddev/blob/main/AGENTS.md) - Go core
- [ddev/ddev.com](https://github.com/ddev/ddev.com/blob/main/AGENTS.md) - Astro website
