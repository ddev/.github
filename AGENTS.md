# AGENTS.md

This file provides guidance to AI agents when working with code in DDEV repositories.

## Communication Style

- Use direct, concise language without unnecessary adjectives or adverbs
- Avoid flowery or marketing-style language ("tremendous", "dramatically", "revolutionary", "working perfectly", etc.)
- Don't include flattery or excessive praise ("excellent!", "perfect!", "great job!")
- State facts and findings directly without embellishment
- Skip introductory phrases like "I'm excited to", "I'd be happy to", "Let me dive into"
- Avoid concluding with summary statements unless specifically requested
- When presenting options or analysis, lead with the core information, not commentary about it

### AI Language Guidelines

- Avoid words that reveal AI writing: "Comprehensive", "works perfectly", "You're absolutely right"
- Don't say "perfect" in response to actions
- Don't claim results are "ready for production use" without verification

## DDEV Project Overview

DDEV is an open-source tool for running local web development environments for PHP and Node.js. It uses Docker containers to provide consistent, isolated development environments with minimal configuration.

For comprehensive developer documentation, see:

- [Developer Documentation](https://docs.ddev.com/en/stable/developers/) - Complete developer guide
- [Add-on Development](https://docs.ddev.com/en/stable/users/extend/creating-add-ons/) - DDEV add-on development guide

## Common DDEV Development Patterns

### Testing

**For Core DDEV Projects:**
- `go test -v ./pkg/[package]` - Test specific package
- `make testpkg TESTARGS="-run TestName"` - Run subset of tests
- `make staticrequired` - Run all required static analysis

**For DDEV Add-ons:**
- `bats tests` - Run add-on tests (primary testing strategy)
- Manual testing: Create test project in `~/tmp/` and install add-on locally
- Test with sample configurations in `tests/testdata/`

### Whitespace and Formatting

- **Never add trailing whitespace** - Blank lines must be completely empty (no spaces or tabs)
- Match existing indentation style exactly (spaces vs tabs, indentation depth)
- Preserve the file's existing line ending style
- Run linting tools to catch whitespace issues before committing

### Development Environment Setup

- **Temporary files**: Use `~/tmp` for temporary directories and test projects
- **Command execution**: For bash commands that don't start with a script or executable, wrap with `bash -c "..."`

## Working with DDEV Repositories

### Branch Naming

Use descriptive branch names that include:

- Date in YYYYMMDD format
- Your GitHub username
- Brief description of the work

Format: `YYYYMMDD_<username>_<short_description>`

Examples:

- `20250925_rfay_move_to_ddev`
- `20250925_username_fix_postgres`
- `20250925_contributor_update_tests`

**Branch Creation Strategy:**

The recommended approach for creating branches is:

```bash
git fetch upstream && git checkout -b <branch_name> upstream/main --no-track
```

This method:

- Fetches latest upstream changes
- Creates branch directly from upstream/main
- Doesn't require syncing local main branch
- Uses --no-track to avoid tracking upstream/main

### Pull Request Creation

When creating pull requests for DDEV repositories, follow the PR template structure:

**Required Sections:**

- **The Issue:** Reference issue number with `#<issue>` and brief description
- **How This PR Solves The Issue:** Technical explanation of the solution
- **Manual Testing Instructions:** Step-by-step guide for testing changes
- **Automated Testing Overview:** Description of tests or explanation why none needed
- **Release/Deployment Notes:** Impact assessment and deployment considerations

**Commit Message Format:**

Follow Conventional Commits: `<type>[optional scope][optional !]: <description>[, fixes #<issue>]`

Examples:

- `fix: handle container networking timeout, fixes #1234`
- `docs: clarify setup instructions`
- `feat: add new service support`

### Pre-Commit Workflow

**For Core DDEV:**
1. Run appropriate tests
2. Run `make staticrequired` (REQUIRED)
3. Fix any issues reported
4. Stage and commit changes

**For DDEV Add-ons:**
1. Run `bats tests` or specific test files
2. Test manually with local installation
3. Fix any issues reported
4. Stage and commit changes

## Security & Configuration Tips

- Do not commit secrets or API keys
- Always use absolute paths when working with repository files
- Focus on surgical, minimal changes that maintain compatibility
- Handle credentials securely in any pull operations or integrations

## Important Instruction Reminders

Do what has been asked; nothing more, nothing less.
NEVER create files unless they're absolutely necessary for achieving your goal.
ALWAYS prefer editing an existing file to creating a new one.
NEVER proactively create documentation files (*.md) or README files. Only create documentation files if explicitly requested by the User.

## Repository-Specific Instructions

Individual repositories may override or extend these instructions with their own AGENTS.md file for project-specific guidance.

## Task Master AI Instructions

**Import Task Master's development workflow commands and guidelines when available:**
[See .taskmaster/CLAUDE.md for details.](./.taskmaster/CLAUDE.md)