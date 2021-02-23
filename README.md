# Spruce Development Process
This repository describes the contribution rules, guidelines, and procedures
that collectively form the development process used at Spruce Systems, Inc. All
engineers contributing to Spruce Systems, Inc. projects are expected to
practice and uphold the Spruce Development Process, henceforth known as "the
process". It is completely fair and even encouraged to call out violations of
the process, from new employee to CEO. PRs to this repository are welcome.

## Process updates
Process updates are currently reviewed, approved, and merged by @wyc.

## Repository etiquette
We use the `git` version control system hosted on GitHub, including its
features
[Issues](https://guides.github.com/features/issues/),
[Pull Requests (PRs)](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/about-pull-requests),
and [Actions](https://docs.github.com/en/actions).

### Working in branches
All work should be completed in separate branches that are short, descriptive,
dash-separated, and prefixed with `feat/` (for features), `bug/`, or `hotfix/`.

Examples of good branch names:
```
feat/refactor-did-resolution
hotfix/parse-utf8-jwt
bug/dup-ctx-caching
```

Examples of bad branch names:
```
my-new-feature (no prefix)
my-new-feature-1 (adding arbitrary '1' to branch name)
feature-set/add_one_function (not dash-separated, invalid prefix)
bug/the-loop-that-runs-one-too-many-times (too verbose)
```

It is preferred that you work in the open from your first commit using the
`[WIP]` PR title prefix and use the task list as recommended. Push your changes
to your branch early and often, force pushing significant progress as is
convenient. This way, the bus factor is reduced, and you are communicating your
changes to other collaborators in closer to real time.

### Commits should be well-formed
Commits should all be well-formed as soon as you remove the `[WIP]` PR title
prefix (see the next section on PRs) and request reviewers. Please see Tim
Pope's [note about commit
messages](https://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html).
Furthermore,

- Make sure you explain why these changes are necessary and their underlying
  goal.
- It is okay to have shorter commit messages (even 1-line messages) for smaller
  changes.
- Each commit should reflect one logical change and not many separate ideas.
- Please add references to issue and pull request numbers to the bottom if your
  commit message if they are relevant.

### Never push to the `main` branch
This would render peer review impossible, and the repository security settings
shouldn't even allow you to do this.

### Creating pull requests
Pull requests are meant to communicate your changes to other developers so they
can peer review and approve merging. They should be written with this audience
in mind.

- Pick a title that succinctly explains your changes.
- Summarize what your one or more commits will do and their purpose.
- Include relevant issue numbers and other PR numbers.
- Do not create massive PRs of high hundreds of lines of changes before getting
  permission from the repository owners. These PRs are difficult and
  painstaking for reviewers to review. Consider splitting your work into
  independent PRs. Exceptions typically granted permissions include major
  refactorings, hotfixes, and independent submodules, but you should ask the
  repository owners before creating your changes.
- It is okay to write a PR dependent on another PR (typically branched off),
  but make sure you include this in the message.
- Include any hints around specific areas or tricky codepaths that you'd
  appreciate extra attention.
- Prefix your PR with `[WIP]` if it is a work in progress and not yet ready for
  review and merging. Consider using the [task list
  feature](https://docs.github.com/en/github/managing-your-work-on-github/about-task-lists)
  to communicate your ongoing progress.
- When your changes are ready for review and merge, remove the `[WIP]` prefix
  and assign at least one reviewer including a repository owner. Only
  repository owners may merge PRs.
- If you are given feedback and are requested to change your work, ensure that
  the commits remain well-formed, and force push to your branch if necessary to
  keep a clean series of commits.
- Always prefer rebasing your branch to `main` to ensure a [linear
  history](https://lists.llvm.org/pipermail/llvm-dev/2019-January/129723.html).
  If you believe a merge commit is a better solution, obtain permission from
  the repository owners to do so.

### Reviewing and merging pull requests
Timely peer review is critical to achieving high quality. When you are
requested to review a PR, you are expected to provide a review within 2
business days by default. This expectation can change if the PR is internally
reprioritized or if you receive explicit approval from a repository owner,
e.g., by emailing or messaging them about it directly. Additionally, as a
reviewer,

- If a PR is too big to review effectively, do not hesitate to ask the author
  to refactor into smaller PRs if independent changes are readily identifiable.
- Make sure you run the code and tests locally, and that it passes any existing
  CI/CD, style checkers, and other automated build process tools.
- Look for test cases to cover new changes introduced. Request more test cases
  if they are low hanging fruit or a new complex feature lacks testing.
- For smaller PRs, using the "Add single comment" feedback is acceptable. For
  larger ones, begin a review, add your comments, and ensure that you click the
  "Finish review" button so your feedback is visible.
- If the commit messages, PR format, or branch conventions violate this
  process, do not hesitate to ask the author to rework their contributions with
  a link to this repository.
- If the PR adds new dependencies, check the dependencies for inclusion
  worthiness.
- Ensure that contributor licenses are signed (should be automatically checked
  by CLA bot when it is live) and that the PR does not introduce license
  changes, such as by modifying the license directly or including
  non-compatible licensed dependencies.
- Anyone can review a pull request, and this is encouraged. Simply add yourself
  to the reviewers even if you were not requested to review. If you are not
  responsive, then you will be removed.

For additional information reviewing the actual code, refer to this [code
review documentation](https://google.github.io/eng-practices/review/reviewer/).
