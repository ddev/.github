# .github

Community Health templates and AI agent instructions for all DDEV repositories.

## Community Health Files

GitHub automatically uses these files as defaults for any DDEV repository that doesn't have its own version:

- `CONTRIBUTING.md` - Contribution guidelines
- `CODE_OF_CONDUCT.md` - Code of conduct
- `ISSUE_TEMPLATE/` - Issue templates
- `PULL_REQUEST_TEMPLATE.md` - PR template
- `SUPPORT.md` - Support information
- `SECURITY.md` - Security policy

For more information, see [GitHub's community health documentation](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file).

## AI Agent Instructions

This repository also provides organization-wide AI agent instructions through the **manual reference pattern**.

### Files

- **`AGENTS.md`** - Base AI agent instructions for all DDEV repositories
- **`CLAUDE.md`** → `AGENTS.md` (symlink for Claude Code compatibility)
- **`.github/copilot-instructions.md`** → `../AGENTS.md` (symlink for GitHub Copilot compatibility)

### Strategy: Manual Reference Pattern

Since AI agent instruction files (`AGENTS.md`, `CLAUDE.md`, `copilot-instructions.md`) are not GitHub community health files, they don't have automatic fallback behavior. Instead, we use a **manual reference pattern** where individual repositories explicitly reference the organization-wide instructions.

**Why this approach:**
- ✅ Works with any Git clone (no broken symlinks between repos)
- ✅ Explicit and discoverable
- ✅ Allows project-specific customization
- ✅ Single source of truth for shared patterns
- ✅ Compatible with all AI tools

### Using in Your DDEV Repository

#### For New Repositories

1. **Create project-specific AGENTS.md:**

```markdown
# AGENTS.md

This file provides guidance to AI agents when working with [PROJECT_NAME].

## Project Overview

[Brief description of your project]

## Project-Specific Development

[Add project-specific content like:]
- Key commands and testing approaches
- Architecture notes
- Special configuration requirements
- Development workflow specifics

## General DDEV Development Patterns

For standard DDEV organization patterns including communication style, branch naming, PR creation, security practices, and common development workflows, see the [organization-wide AGENTS.md](https://github.com/ddev/.github/blob/main/AGENTS.md).

## Important Instruction Reminders

Do what has been asked; nothing more, nothing less.
NEVER create files unless they're absolutely necessary for achieving your goal.
ALWAYS prefer editing an existing file to creating a new one.
NEVER proactively create documentation files (*.md) or README files. Only create documentation files if explicitly requested by the User.
```

2. **Create tool-specific symlinks:**

```bash
# For Claude Code compatibility
ln -s AGENTS.md CLAUDE.md

# For GitHub Copilot compatibility
mkdir -p .github
ln -s ../AGENTS.md .github/copilot-instructions.md
```

#### For Existing Repositories

1. **Update existing AGENTS.md** to include reference to org-wide version
2. **Remove duplicated content** that's now covered by the org-wide file
3. **Keep project-specific content** (testing, architecture, special workflows)
4. **Ensure tool symlinks exist** as shown above

### Examples

- **[ddev/ddev](https://github.com/ddev/ddev/blob/main/AGENTS.md)** - Core DDEV with Go development, Docker architecture
- **[ddev/ddev-upsun](https://github.com/ddev/ddev-upsun/blob/main/AGENTS.md)** - Add-on with Bats testing, PHP actions, Upsun integration

### Content Organization

**Organization-wide AGENTS.md covers:**
- Communication style and AI language guidelines
- Branch naming conventions
- Pull request creation workflows
- Security and configuration practices
- Common development environment setup
- General troubleshooting patterns

**Project-specific AGENTS.md should cover:**
- Project architecture and key components
- Specific testing strategies and commands
- Build processes and validation workflows
- Domain-specific development patterns
- Integration with external services or platforms

### Maintenance

- **Update shared patterns** in this organization-wide AGENTS.md
- **Individual repositories** automatically benefit through references
- **Project-specific content** remains in individual repository files
- **No complex automation** or synchronization required
