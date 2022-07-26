# Index

- [Index](#index)
- [About](#about)
- [Creating A New Repo: Initial Branching](#creating-a-new-repo-initial-branching)
- [Branch Semantics And Policies](#branch-semantics-and-policies)
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

+ `latest`
  + This is the `release` branch containing all the stable releases.
  + It is the `default` branch
  + It branches to `tst`
  + It is the `compare` branch, meaning all other branches compare to the release branch individually (number of commits behind/ahead).
  + The branch is **permanent**.
  + ~~`delete`~~
  + ~~`push`/`commit`~~
  + `pull`
  + `merge`: `latest ⇄ tst/*` iff:
    + All `tst/*` tests are passing
    + No conflicts
+ `tst`
  + This is the `test` branch that merges all the `features`.
  + It branches from `latest`
  + It branches to `dev`
  + The branch is **permanent**.
  + ~~`delete`~~
  + ~~`push`/`commit`~~
  + `pull`
  + `merge` from `dev/*` only such that:
    + All `dev/*` tests are passing
    + No conflicts
+ `dev`
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
+ `feature/*`
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
+ `task/*`
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
+ `subtask/*`
  + This is the `subtask` branch that merges all the subtask's `commits`.
  + The branch is **temporary**.
  + `delete`
  + `push`/`commit`
  + `pull`
  + `merge` from `task/*` only such that:
    + All `task/*` tests are passing
    + No conflicts
+ `issue/*`
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