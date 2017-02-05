## Welcome!

I'm so glad you've found this project interesting and useful enough that you'd
like to contribute to its development.

Please take time to review the policies and procedures in this document prior
to making and submitting any changes.

This guide was drafted with tips from [Wrangling Web Contributions: How to
Build a CONTRIBUTING.md](https://mozillascience.github.io/working-open-workshop/contributing/)
and with some inspiration from [the Atom project's CONTRIBUTING.md
file](https://github.com/atom/atom/blob/master/CONTRIBUTING.md).

## Table of contents

- [Quick links](#quick-links)
- [Code of conduct](#code-of-conduct)
- [Reporting issues](#reporting-issues)
- [Updating documentation](#updating-documentation)
- [Environment setup](#environment-setup)
- [Workflow](#workflow)
- [Testing](#testing)
- [Coding conventions](#coding-conventions)
- [Open Source License](#open-source-license)

## Quick links

- [README](README.md)
- [Code of conduct](CODE_OF_CONDUCT.md)
- [License information](LICENSE.md)
- [Original repository](https://github.com/mbland/certbot-webroot-setup/)
- [Issues](https://github.com/mbland/certbot-webroot-setup/issues)
- [Pull requests](https://github.com/mbland/certbot-webroot-setup/pulls)
- [Issues](https://github.com/mbland/certbot-webroot-setup/issues)

## Code of conduct

Harrassment or rudeness of any kind will not be tolerated, period. For
specifics, see the [CODE_OF_CONDUCT](CODE_OF_CONDUCT.md) file.

## Reporting issues

Before reporting an issue, please use the search feature on the [issues
page](https://github.com/mbland/certbot-webroot-setup/issues) to see if an issue
matching the one you've observed has already been filed.

If you do find one...

### Do not add a +1 comment!

If you find an issue that interests you, but you have nothing material to
contribute to the thread, use the *Subscribe* button on the right side of the
page to receive notifications of further conversations or a resolution. Comments
consisting only of "+1" or the like tend to clutter the thread and make it more
painful to follow the discussion.

If you _do_ have something to add to the conversation, or _don't_ find a
matching issue...

### Update an existing issue or file a new one

Try to be as specific as possible about your environment and the problem you're
observing. At a minimum, include:

- The version of bash you're using, from either `bash --version` or `echo
  $BASH_VERSION`
- The version of `certbot-webroot-setup` you're using
- Command line steps or code snippets that reproduce the issue

Also consider using:

- bash's `time` builtin to collect running times
- a regression test to add to the suite
- memory usage as reported by a tool such as
  [memusg](https://gist.github.com/netj/526585)

## Updating documentation

If you've a passion for writing clear, accessible documentation, please don't be
shy about sending pull requests! The documentation is just as important as the
code, especially in this project, since the goal is to make the functionality as
discoverable as possible through the `./certbot-webroot-setup help` command.

Also: _no typo is too small to fix!_ Really. Of course, batches of fixes are
preferred, but even one nit is one nit too many.

## Environment setup

Make sure you have Bash installed per the [Environment setup in the
README](README.md#environment-setup).

You will also need [Git](https://git-scm.com/downloads) installed on your
system. If you are not familiar with Git, you may wish to reference the [Git
documentation](https://git-scm.com/doc).

## Workflow

The basic workflow for submitting changes resembles that of the [GitHub Git
Flow](https://guides.github.com/introduction/flow/), except that you will be
working with your own fork of the repository and issuing pull requests to the
original.

1. Fork the repo on GitHub (look for the "Fork" button)
2. Clone your forked repo to your local machine
3. Create your feature branch (`git checkout -b my-new-feature`)
4. Develop _and [test](#testing)_ your changes as necessary.
4. Commit your changes (`git commit -am 'Add some feature'`)
5. Push to the branch (`git push origin my-new-feature`)
6. Create a new [GitHub pull
   request](https://help.github.com/articles/using-pull-requests/) for your
   feature branch based against the original repository's `master` branch
7. If your request is accepted, you can [delete your feature
   branch](https://help.github.com/articles/deleting-unused-branches/) and
   pull the updated `master` branch from the original repository into your
   fork. You may even [delete your
   fork](https://help.github.com/articles/deleting-a-repository/) if you don't
   anticipate making further changes.

## Testing

No bug fixes or new features will be accepted without accompanying tests.
Period.

Any changes that break the continuous integration build must be fixed or rolled
back immediately.

This project uses the [Bash Automated Testing System
(Bats)](https://github.com/sstephenson/bats) to write and run tests. All tests
and helper scripts are in the `tests/` directory and are run using the `./go
test` command. This command has a very flexible syntax for running a subset of
test suites (i.e. a set of test cases within individual `.bats` files or
directories). Enabling tab completion via `./go env` is highly encouraged.

Before sending your code for review, make sure to run the entire test suite via
`./go test`. If you're on a Linux system that uses the `apt-get` package manager
(e.g. Ubuntu, Debian), run `./go test --coverage` to make sure your changes are
adequately covered by new and existing tests. This will install (within the
project working directory) and run the
[kcov](https://github.com/SimonKagstrom/kcov) tool, which is only available on
Linux for now.

## Coding conventions

Follow [the conventions laid out in the go-script-bash CONTRIBUTING.md
file](https://github.com/mbland/go-script-bash/blob/master/CONTRIBUTING.md#coding-conventions).

## Open Source License

This software is made available as [Open Source
software](https://opensource.org/osd-annotated) under the [ISC
License](https://www.isc.org/downloads/software-support-policy/isc-license/).
For the text of the license, see the [LICENSE](LICENSE.md) file.
