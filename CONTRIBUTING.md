# Contributing to DDEV

Thank you for helping. This guide applies to every repository in the
[DDEV organization](https://github.com/ddev), including the add-ons. Some
repositories, like [ddev/ddev](https://github.com/ddev/ddev/blob/main/CONTRIBUTING.md),
have their own `CONTRIBUTING.md` that adds how to build and test that project.

## Getting Help

For questions, start with the [DDEV documentation](https://docs.ddev.com) and
the [DDEV Discord](https://ddev.com/s/discord), where most of the community and
the maintainers spend their time. See
[Support](https://docs.ddev.com/en/stable/users/support/) for other places to
ask.

## Reporting Issues

Open an issue for bugs, confusing documentation, and feature requests.

- **Search first.** Check open and closed issues; your problem may already be
  reported or fixed. If an open issue matches, add a reaction rather than a
  "me too" comment, unless you have new information.
- **Use the template** and fill it in completely. It asks for the details a
  maintainer would otherwise have to ask you for.
- **Include diagnostics.** For a problem with DDEV itself, run
  `ddev utility test` and share its output, either in the issue or in a
  [Gist](https://gist.github.com).
- **Say what you expected and what happened instead**, with the exact steps to
  reproduce it.

## Pull Requests

- **Discuss larger changes first**, in an issue or on Discord, before you
  invest time in them. A small fix can go straight to a pull request.
- **Keep a pull request to one change.** Unrelated fixes are easier to review,
  and to revert, as separate pull requests.
- **Follow the pull request template**, and title the pull request using
  [Conventional Commits](https://docs.ddev.com/en/stable/developers/building-contributing/#pull-request-title-guidelines).
  The title becomes the commit message on the main branch.
- **Test your change**, and add tests where the repository has them.
- **Respond to review** by pushing more commits to the same branch.

Not every pull request is merged. A maintainer may already be working on the
same thing, or the change may not fit the project's direction. Either way, you
will get an explanation.

## Using AI Tools

DDEV accepts contributions written with the help of AI tools. **You are
responsible for everything you submit**, however it was produced:

- **Understand the change.** You must be able to explain what every line does,
  why it is needed, and how it affects the rest of the code, without going back
  to the tool.
- **Run and test it yourself** before opening the pull request. Do not leave it
  to maintainers to find out whether generated code works.
- **Review the description too.** Make sure the pull request description says
  only what is true of the change, at a length a reviewer will read.
- **Answer review in your own words.** Do not paste a tool's response to a
  reviewer's question.
- **Disclose substantial AI assistance** in the pull request description, for
  example with a line naming the tool you used.

Pull requests that look like unreviewed AI output may be closed without a
detailed review. The same standards apply to issues and comments.

## Code of Conduct

Everyone taking part in DDEV is expected to follow the
[Code of Conduct](https://docs.ddev.com/en/stable/users/code-of-conduct/).

## Licensing

By contributing, you agree that your contribution is licensed under the license
of the repository you are contributing to, and that you have the right to
contribute it under that license.
