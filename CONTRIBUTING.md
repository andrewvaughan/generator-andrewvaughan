# Contributing

[This project][github-project] would not exist without its contributors, and we welcome you to join us in our
endeavor. This guide is intended for anyone who wants to contribute, in any way, whether directly or indirectly.
Please read this document carefully before contributing, as it answers many of the questions that new contributors
have when first working with our projects.

Afterwards, if any questions persist, please feel free to join our [Gitter][gitter] rooms for discussion.

---

## Agreement

By submitting any work to this project, you agree to our [project license][github-license] as well as to the following
principal guidelines:

1. Any work contributed is original work, or you otherwise have the right to submit the work;
1. You grant this project and its members a non-exclusive, irrevocable license to use your submitted work in any way; and,
1. You are capable of granting these rights for the contribution.

---

## Ways to Contribute

There are many ways to contribute to this project:

* **Report a Bug** - if you find a bug, please [file a detailed issue](#bug-reports)
* **Request a Feature** - if you want to request a feature, please [submit a request](#feature-requests)
* **Work on an Issue** - if you wish to contribute directly, please feel free to work on [any open issue](#working-on-issues)

### Bug Reports

Perfect code is rare, and this project is no exception. If you find a bug, or feel something is acting strangely,
please [file an issue][gh-issues] so that it can be addressed. When filing an issue, please complete the provided
template as closely as feasible to provide the development team enough information to replicate your need.

### Feature Requests

We love ideas of any form. Even if you cannot add a feature on your own, we welcome all suggestions. When making a
feature request, please [file an issue][github-issues] and provide the following information:

* The feature you want to add or problem you want to solve
* Your take on the correct approach to building the new functionality

---

## Working on Issues

All bugs and features are stored in our [GitHub Issues][github-issues] section. It is here that we determine which
issues will be road-mapped for various releases and plan our milestones and versions accordingly. Releases can be
found on the [GitHub Releases][github-releases] page. All issues that are received will be reviewed by the core
development staff and assigned a milestone and a version for release.

If you intend to work on a specific issue, please add a comment to the issue saying so and indicate when you think
you will complete it. This will help us to avoid duplication of effort. If you find that you cannot finish the work,
simply add a comment letting people know so someone else can pick it up.

### Pull Requests

All contributions to this project must go through a [GitHub Pull Request][github-pulls]. In addition, all Pull
Requests must be directly related to an open issue. You should familiarize yourself with the [GitFlow][gitflow] model
and [rebase merges][rebase] before getting started. While your commits will be rebased and squashed as part of the
Pull Request process, you may optionally [squash][squash] them yourself before submitting.

**1. Open or choose an issue to work on**

Before working, please identify or create an issue for what you are looking to contribute.

> **Note** that only accepted issues will be merged, and if your issue is not slated for a version and a milestone, it
> may not be accepted. You may request that the issue be identified for release before you begin working.

**2. Announce that you will be working on that issue**

Let us know when you plan to start on the issue and how long you think it will take you. This will help us be ready
to support you when it comes time to review.

**3. Fork the project repository and initialize GitFlow**

Every contributor, including core staff, is required to work within a fork of their own repository. All branches on
the main repository are meant for distribution purposes only. See [this page][fork] for details on forking a
repository on GitHub.

Assuming you have the [Git Flow Plugin][gitflow-plugin] properly installed, you can clone this freshly-forked
repository and set it up for Git Flow as follows:

```bash
git clone git@github.com:<your-username>/generator-andrewvaughan.git
cd generator-andrewvaughan
git flow init
```

When initializing, all projects should use the following configurations:

| Configuration                               | Setting    |
|--------------------------------------------:|:----------:|
| Branch name for production releases:        | `master`   |
| Branch name for "next release" development: | `develop`  |
| Feature branches                            | `feature/` |
| Release branches                            | `release/` |
| Documentation branches                      | `docs/`    |
| DevOps branches                             | `devops/`  |
| Hotfix branches                             | `hotfix/`  |
| Support branches                            | `bugfix/`  |
| Version tag prefix                          | `v`        |

*Note* That the branch standards above expand on the GitFlow standard set.

**4. Add the project upstream remote**

In order to keep your code up to date with the project's `develop` branch, you need to add the project's main
repository as your upstream:

```bash
git remote add upstream https://github.com/andrewvaughan/generator-andrewvaughan.git
git fetch upstream
```

**5. Ensure that your `develop` branch is up to date with the upstream**

When starting a new branch, it is important to ensure you are branching from the latest version of the project's
`develop` branch:

```bash
git fetch --all
git checkout develop
git pull upstream develop
```

**6. Create a new branch**

Use the `git-flow` plugin to create an appropriate branch for your work. For instance, if you are creating a
`feature` branch, you might create the branch as follows:

```bash
git flow feature start my-new-feature
```

This will create the `feature/my-new-feature` branch on your local computer. To make sure you track this correctly
with your personal, forked repository, publish it:

```bash
git flow feature publish my-new-feature
```

This branch name is your discretion, but descriptive names will help users ensure correct context when working.

**7. Make your changes**

Make your changes, add tests, and commit! All features must be tested to completion before they will be accepted.
This project makes use of automated testing tools to provide thorough testing and code-style rules to ensure
consistency across the project.

Please refer to our [code standards](#code-style-requirements) to save yourself time when testing!

**8. Rebase onto upstream**

Before you send a pull request, be sure to rebase onto the upstream source. This ensures your code is running on
the latest available code and is compatible with the latest codebase. This also ensures your Pull Request will not be
rejected:

```bash
git fetch upstream
git rebase upstream/develop
```

**9. Ensure all tests pass**

After rebasing, be sure to run the test suite to make sure nothing is broken. You need to ensure that your coverage
and tests do not fail on the latest project `develop` branch.

**10. (Optional) Squash your commits**

Commits on the production environment are used as a change log for releases. As such, commits must be
[squashed][squash] to a single commit before being accepted. This is usually done as part of the Pull Request process,
but you may optionally squash your commits before submitting.

If squashed, on the last step of your rebase, all commit messages must follow a specific standard to be accepted:

```
Tag: Message (closes #issueno)
```

In this case, `Tag` is one of the following:

* `Fix` - for a bug fix
* `Update` - for any update to existing functionality
* `New` - for any new functionality
* `Docs` - for documentation updates
* `DevOps` - for changes to build or automation (or general operational changes)
* `Upgrade` - for dependency upgrades

The `Message` should be a one-sentence description of the change. Finally, the issue number the Pull Request
represents should be mentioned at the end. If the commit does not completely resolve the issue, please use
`(refs #1234)` instead of `(closes #1234)`. Alternatively, with bugs, you may choose to use `fixes` instead of
`closes`.

Here are some good examples:

```
DevOps: Added new Python version to Travis-CI config (closes #19)
Fix: Resolved bug due to extra semicolon (fixes #220)
Upgrade: Upgraded (some pip module) from 1.0.0 to 1.1.0 (closes #999)
Docs: Added license data to readme as part of new licensing project (refs #42)
```

**11. Submit a Pull Request**

You're ready to submit your pull request! Refer to the [GitHub documentation][pull-request] on how best to send a pull
request from your fork.

**12. Watch and communicate**

All Pull Requests must pass comprehensive testing. If the build passes or fails, it will show up on the Pull
Request. We cannot accept any Pull Requests that fail our criteria for a build, so if that happens, please fix and
re-squash your commits, and then update the Pull Request to automatically trigger another integration build.

---

## Code Style Requirements

All code provided to this project must follow a strict set of code standards to prevent unnecessary commit logs from
being introduced due to formatting. The project codebase is checked against linting rules before running unit tests.

Before submitting a Pull Request, all tests must be run, provide full coverage of functionality, and successfully
pass before a request will be reviewed.

### Standards Subject to Change

With every Pull Request, the core team has the opportunity to better refine our style and acceptance guidelines. As
such, you may be requested to pull an updated set of code style guidelines due to an unforeseen inconsistency in
submitted code, and to resubmit your request according to the new guidelines.




[gitter]:          https://gitter.im/andrewvaughan/generator

[github-issues]:   https://github.com/andrewvaughan/generator-andrewvaughan/issues
[github-license]:  LICENSE
[github-project]:  https://github.com/andrewvaughan/generator-andrewvaughan
[github-pulls]:    https://github.com/andrewvaughan/generator-andrewvaughan/pulls
[github-releases]: https://github.com/andrewvaughan/generator-andrewvaughan/releases

[gitflow]:        https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow
[gitflow-plugin]: https://github.com/petervanderdoes/gitflow-avh/wiki/Installation
[rebase]:         https://thoughtbot.com/blog/git-interactive-rebase-squash-amend-rewriting-history
[fork]:           https://help.github.com/en/articles/fork-a-repo
[squash]:         http://gitready.com/advanced/2009/02/10/squashing-commits-with-rebase.html
[pull-request]:   https://help.github.com/en/articles/creating-a-pull-request
