# AGENTS.md

Organization-wide guidance for AI agents working in DDEV repositories. A
repository's own `AGENTS.md` takes precedence over this file. DDEV docs:
[developers](https://docs.ddev.com/en/stable/developers/),
[add-ons](https://docs.ddev.com/en/stable/users/extend/creating-add-ons/).

## Boundaries

- **Never** commit secrets, API keys, or `.env` files.
- **Never** leave trailing whitespace; blank lines must be empty.
- **Ask first** before `git push` or any other command that publishes to a
  remote, and push only after the user explicitly confirms.
- **Always** run the repository's lint and test commands for the code you
  changed before committing.
- **Always** put temporary files and test projects in `~/tmp`.

## Code and files

- Make the smallest change that solves the task, and keep existing behavior
  compatible.
- Match the file's indentation, line endings, and surrounding style.
- Fetch GitHub files from `raw.githubusercontent.com`, not
  `github.com/.../blob/...` pages.

## Writing style

Applies to conversation, commit messages, PR and issue text, docs, and code
comments.

- Lead with the substance. Skip introductions, compliments, and closing
  summaries unless asked.
- Report results plainly, including what failed, was skipped, or is
  unverified.
- **Never use:** `comprehensive`, `seamless`, `genuine(ly)`, `honest(ly)`,
  `truly`, `really` (as an intensifier), `perfect(ly)`, `robust`, `powerful`,
  `effortless`, `production-ready`, `tremendous`, `dramatically`,
  `revolutionary`, `delve`, `elevate`, `unleash`. Delete the word; if the
  sentence then loses meaning, add evidence instead.

## Branches and commits

Name branches `YYYYMMDD_<username>_<short_description>`, for example
`20250925_rfay_fix_postgres`, and create them from upstream (use `origin` when
there is no `upstream` remote):

```bash
git fetch upstream && git checkout -b <branch_name> upstream/main --no-track
```

Write commit titles in [Conventional Commits](https://www.conventionalcommits.org/)
format:
`<type>[optional scope][optional !]: <description>[, fixes #<issue>][, for #<issue>]`,
with type one of `build`, `chore`, `ci`, `docs`, `feat`, `fix`, `perf`,
`refactor`, `style`, `test`. Write the description in the imperative, start
it lowercase, and end it without a period. For example:
`fix: handle container networking timeout, fixes #1234`. Main-branch titles
generate the release changelog, so describe the change for users.

## Pull requests and issues

- Write the first commit's body as the PR description, following the
  repository's `.github/PULL_REQUEST_TEMPLATE.md` or the
  [organization default](https://raw.githubusercontent.com/ddev/.github/main/PULL_REQUEST_TEMPLATE.md).
  For issues, use the field labels of the repository's issue form as
  headings.
- Always fill in "Short Summary (TL;DR)". Omit other sections that don't
  apply, headings included.
- Explain why the change was made and what to check by hand, not what the diff
  already shows.
- Pass bodies from a file: `git commit -F <file>`,
  `gh pr create --body-file <file>`, `gh issue create --body-file <file>`.
- In commit, PR, and issue bodies, keep each paragraph on one line; GitHub
  turns every line break inside a paragraph into `<br>`.
- When amending a commit, re-check every claim in its body against the
  current diff.
- After adding commits to a branch with an open PR, re-read the PR body
  against the whole branch diff, and update it with
  `gh pr edit --body-file <file>` if a claim is no longer true.

## AI attribution

End commit messages and PR descriptions with a line naming and linking the AI
tool you are running in. In commits only, add a `Co-Authored-By` trailer
naming the model in use and your vendor's noreply address; skip the trailer if
you don't know that address.

```text
🤖 Developed with assistance from [<tool>](<tool URL>)

Co-Authored-By: <model> <<vendor noreply address>>
```

For example, Claude Code writes `[Claude Code](https://claude.ai/code)` and
`Co-Authored-By: Claude <model> <noreply@anthropic.com>`.
