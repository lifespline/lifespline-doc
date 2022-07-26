# Index

- [Index](#index)
- [About](#about)
- [Creating A New Repo: Initial Branching](#creating-a-new-repo-initial-branching)
- [Branch Semantics And Policies](#branch-semantics-and-policies)
  - [`latest`](#latest)
  - [`release/*`](#release)
  - [`tst`](#tst)
  - [`dev`](#dev)
  - [`feature/*`](#feature)
  - [`task/*`](#task)
  - [`subtask/*`](#subtask)
  - [`issue/*`](#issue)
- [Pull Requests and Merging Remarks](#pull-requests-and-merging-remarks)
- [Commit Semantics And Rules](#commit-semantics-and-rules)
- [Semantic Versioning](#semantic-versioning)
- [Testing](#testing)
- [Linting](#linting)
- [Formatting](#formatting)
- [Debugging](#debugging)
- [Editing](#editing)

# About

The guide shows how the repository is setup.

# Creating A New Repo: Initial Branching

When you create a new repo, branch as:

```
latest
│
├╴ tst
│  │   
│  ├╴ release/*
│  │  │
│  │  ├╴ task/* [optional]
│  │  │  ┊
│  │  │  commit
│  │  │
│  │  ├╴ task/* [optional]
│  │  │  │
│  │  │  ├╴ subtask/* [optional]
│  │  │  │  ┊
│  │  │  │  commit
│  │  │  │  commit
│  │  │  ┊
│  │  ┊
│  │  commit
│  │
│  ├╴ dev
│  │  │
│  │  ├╴ feature/*
│  │  │  │
│  │  │  ├╴ task/*
│  │  │  │  ┊
│  │  │  │  commit
│  │  │  │
│  │  │  ├╴ task/*
│  │  │  │  │
│  │  │  │  ├╴ subtask/* [optional]
│  │  │  │  │  ┊
│  │  │  │  │  commit
│  │  │  │  │  commit
│  ┊  ┊  ┊  ┊
│
├╴ issue/*
┊
```

The example below has the following structure:

```
latest
├╴ tst
│  ├╴ dev
│  │  ├╴ feature/init_readme
│  │  │  ├╴ task/wipe_readme
│  │  │  ├╴ task/write_readme
```

![image][init-repo]

Mind that the `feature/*` and `task/*` branches were created through the [backlog tasks][backlog] so the tasks can be traced back to the repository. Read more about branching the tasks and about the branching policies in [branching policies](#branching-policies).

# Branch Semantics And Policies

A branch encapsulates a **unit of work**, be it a `feature`, a `task` or a `subtask`. The developer is encouraged to add branches the descriptions added in the scrum board by running:

```shell
$ git branch --edit-description
```

Which opens a CLI editor so that the description be persisted:

```txt
multiline branch
description here
# Please edit the description for the branch
#   feature/bootstrap_template
# Lines starting with '#' will be stripped.
```

The branch semantics and policies follow below:

## `latest`
  + `description`: The `latest` branch is a repository for stable and versioned releases from `release/*` (or from `tst` directly).
  + It is the `default` branch
  + `branch`: `tst`
  + It is the `compare` branch, meaning all other branches compare to the release branch individually (number of commits behind/ahead).
  + The branch is **permanent**.
  + ~~`delete`~~
  + ~~`push`/`commit`~~
  + `pull`
  + `merge`: `latest ⇄ tst/*` iff:
    + All `tst/*` tests are passing
    + No conflicts
  +  Created by: `product-owner`
## `release/*`
  + `description`: This is the `release` branch. As features are merged together in `tst`, `release/*` encapsulates a new release independent from previous releases. Each release contains a `changelog.md` that documents breaking changes, enhancements, *etc.*. `latest` is simply a historic of releases, but that historic is not sufficient to understand the dependencies between the releases. Read `changelog.md` for the dependency tree.
  + `branch`: `tst`
  + The branch is **temporary**.
  + ~~`delete`~~
  + ~~`push`/`commit`~~
  + `pull`
  + `merge` from `dev/*` only such that:
    + All `dev/*` tests are passing
    + No conflicts
  + Created by: `product-owner`
## `tst`
  + This is the `test` branch that merges all the `features`.
  + `branch`: `latest`
  + The branch is **permanent**.
  + ~~`delete`~~
  + ~~`push`/`commit`~~
  + `pull`
  + `merge` from `dev/*` only such that:
    + All `dev/*` tests are passing
    + No conflicts
  + ~~`description`~~ The description is a default description
  + Created by: `product-owner`
## `dev`
  + This is the `development` branch that merges all the feature `tasks`.
  + It branches from `tst`
  + It branches to `feature/*`
  + The branch is **permanent**.
  + ~~`delete`~~
  + ~~`push`/`commit`~~
  + `pull`
  + `merge` from `feature/*` only such that:
    + All `feature/*` tests are passing
    + No conflicts
  + ~~`description`~~ The description is a default description
  + Created by: `product-owner`
## `feature/*`
  + This is the `feature` branch that merges all the feature `tasks`.
  + It branches from `dev`
  + It branches to `task/*`
  + The branch is **temporary**.
  + `delete`
  + `push`/`commit`
  + `pull`
  + `merge` from `task/*` only such that:
    + All `task/*` tests are passing
    + No conflicts
  + `description`
    + Created by the `product-owner` only
    + high-level description
    + `DOD`
  + Created by: `product-owner`
## `task/*`
  + This is the `task` branch that merges all the task's `commits` or the task's `subtasks`.
  + It branches from `feature/*`
  + It branches optionally to `subtask/*`
  + The branch is **temporary**.
  + `delete`
  + `push`/`commit`
  + `pull`
  + `merge` from `subtask/*` only such that:
    + All `subtask/*` tests are passing
    + No conflicts
  + `description`
    + high-level description
    + `DOD`
  + Created by: `dev`
## `subtask/*`
  + This is the `subtask` branch that merges all the subtask's `commits`.
  + The branch is **temporary**.
  + `delete`
  + `push`/`commit`
  + `pull`
  + `merge` from `task/*` only such that:
    + All `task/*` tests are passing
    + No conflicts
  + `description`
    + high-level description
    + `DOD`
  + Created by: `dev`
## `issue/*`
  + This is the `subtask` branch that merges all the subtask's `commits`.
  + It branches from `latest`
  + It branches to `latest`
  + The branch is **temporary**.
  + `delete`
  + `push`/`commit`
  + `pull`
  + `merge` from `latest` only such that:
    + `ISSUES.md` linting is passing
    + no conflicts
  + `description`
    + high-level description
    + `DOD`
  + Created by: `dev`, `product-owner`
  + The `dev` and `tst` will deviate from `latest` because they won't contain the commits to `ISSUES.md`, unless a `PR` is issued to `dev` and `tst` successively.

```
latest
│
├╴ tst
│  │
│  ├╴ dev
│  │  │
│  │  ├╴ feature/*
│  │  │  │
│  │  │  ├╴ task/*
│  │  │  │  ┊
│  │  │  │  commit
│  │  │  │
│  │  │  ├╴ task/*
│  │  │  │  │
│  │  │  │  ├╴ subtask/* [optional]
│  │  │  │  │  ┊
│  │  │  │  │  commit
│  │  │  │  │  commit
```

# Pull Requests and Merging Remarks

It goes without saying, but merging your work from `A` into a contribution branch `B` with a `PR`, start by pulling `B` and merging with `A` to guarantee all tests are still passing and that there are no merging conflicts. If this is the case, submit a `PR` from `A` to `B`. This will reduce the `PR`s waiting for errors to be fixed before merging. After merging the `PR`, pull the changes merged with `B` and delete `A` if it was also deleted in remote.

# Commit Semantics And Rules

# Semantic Versioning

Read more at [semantic versioning][semantic_versioning.md].

# Testing

Read more at [testing][testing.md].

# Linting

Read more at [linting][linting.md].

# Formatting

Read more at [formatting][formatting.md].

# Debugging

Read more at [debugging][debugging.md].

# Editing

Read more at [editing with VSCode][vscode.md].

[init-repo]: img/init_repo.png "Initialize a repositories branches"
[backlog]: https://dev.azure.com/novonordiskit/CMC%20Data%20Foundation/_backlogs/backlog/CMC%20Data%20Foundation%20Team/Epics