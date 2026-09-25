# Git Log

## What is `git log`?

`git log` is used to **view the commit history of a Git repository**.

### Simple Definition

> **`git log` = See what was committed in the past.**

---

# Basic Command

```bash
git log
```

It shows information about previous commits.

Example:

```text
commit a82f321...
Author: Aditya
Date: ...

    Add login page

commit c71ab92...
Author: Aditya
Date: ...

    Add navbar

commit b52cd11...
Author: Aditya
Date: ...

    Initial commit
```

---

# What Information Does `git log` Show?

A normal `git log` can show:

- Commit hash
    
- Author
    
- Date
    
- Commit message
    

Example:

```text
commit a82f321
Author: Aditya
Date: ...

    Add login page
```

---

# Commit Hash

Every commit has a unique identifier called a **commit hash**.

Example:

```text
a82f321
```

The full hash is much longer, but Git often displays a shortened version.

You can use a commit hash to inspect a particular commit.

```bash
git show a82f321
```

---

# `git log --oneline`

The normal `git log` output can be long.

Use:

```bash
git log --oneline
```

Example:

```text
a82f321 Add login page
c71ab92 Add navbar
b52cd11 Initial commit
```

This is one of the most useful ways to quickly read commit history.

---

# Understanding the Order

Suppose you see:

```text
a82f321 Add login page
c71ab92 Add navbar
b52cd11 Initial commit
```

The top commit is the **newest** commit.

The bottom commit is older.

So:

```text
Newest
  ↓
a82f321
c71ab92
b52cd11
  ↓
Oldest
```

---

# View a Specific Commit

Use:

```bash
git show <commit-id>
```

Example:

```bash
git show a82f321
```

This shows information about that commit and the changes it introduced.

---

# `git log --stat`

To see which files were changed by each commit:

```bash
git log --stat
```

This gives you a summary of file changes.

---

# `git log --patch`

To see the actual changes introduced by commits:

```bash
git log -p
```

This can produce a lot of output because it shows patch/diff information.

---

# `git log --graph`

To visualize branch history:

```bash
git log --graph
```

For a compact graph:

```bash
git log --oneline --graph
```

Example:

```text
* a82f321 Add login
* c71ab92 Add navbar
* b52cd11 Initial commit
```

---

# See All Branches

Use:

```bash
git log --oneline --graph --all
```

Example:

```text
* a82f321 Add login
* c71ab92 Add navbar
| * d71ca22 Add payment
|/
* b52cd11 Initial commit
```

This is useful for understanding how branches developed.

---

# `git log` for a Specific Branch

You can specify a branch:

```bash
git log main
```

Or:

```bash
git log feature-login
```

For a short version:

```bash
git log --oneline feature-login
```

---

# See Recent Commits

You can limit the number of commits:

```bash
git log -5
```

This shows approximately the last 5 commits.

With one-line output:

```bash
git log --oneline -5
```

Example:

```text
a82f321 Add login
c71ab92 Add navbar
b52cd11 Initial commit
```

---

# Search Commit Messages

You can search commit messages using:

```bash
git log --grep="login"
```

This finds commits whose messages contain `login`.

Example:

```text
a82f321 Add login page
d52bc21 Fix login validation
```

---

# See Commits by Author

You can filter by author:

```bash
git log --author="Aditya"
```

This shows commits matching that author.

---

# See Commits in a Date Range

You can use:

```bash
git log --since="2026-01-01"
```

or:

```bash
git log --since="1 week ago"
```

You can also specify an end date:

```bash
git log --since="2026-01-01" --until="2026-02-01"
```

---

# Compare Two Points in History

You can inspect commits between two references.

Example:

```bash
git log main..feature-login
```

This shows commits reachable from `feature-login` that are not reachable from `main`.

This is useful for understanding what a feature branch contains beyond another branch.

---

# `git log` vs `git show`

### `git log`

Shows the history:

```bash
git log --oneline
```

Example:

```text
A Add login
B Add navbar
C Initial commit
```

### `git show`

Shows details of a specific commit:

```bash
git show A
```

Think:

```text
git log
   ↓
"What commits happened?"

git show
   ↓
"What did this particular commit do?"
```

---

# `git log` vs `git status`

### `git status`

Shows the current state:

```bash
git status
```

### `git log`

Shows commit history:

```bash
git log
```

Remember:

```text
status → What's happening now?
log    → What happened before?
```

---

# Example Project History

Suppose you worked on your project for several days:

```text
Day 1
Initial project

Day 2
Add navbar

Day 3
Add authentication

Day 4
Fix authentication bug
```

Your Git history might look like:

```text
a82f321 Fix authentication bug
c71ab92 Add authentication
b52cd11 Add navbar
8f21abc Initial project
```

You can inspect it using:

```bash
git log --oneline
```

---

# Useful `git log` Commands

```bash
# Full history
git log

# Compact history
git log --oneline

# Graph
git log --oneline --graph

# All branches
git log --oneline --graph --all

# Last 5 commits
git log --oneline -5

# Show file changes statistics
git log --stat

# Show actual patches
git log -p

# Search commit messages
git log --grep="login"

# Filter by author
git log --author="Aditya"

# Show branch history
git log feature-login
```

---

# Aadi Bhai Example 😎

Imagine your project is a notebook.

Every time you finish an important change, you write:

```text
Page 1 → Initial project
Page 2 → Add navbar
Page 3 → Add login
Page 4 → Fix login
```

Git's commit history is like that record.

When you run:

```bash
git log --oneline
```

Git shows your project's previous save points.

---

# Aadi Bhai Memory Trick

Remember:

```text
git log
   ↓
Commit History
   ↓
"What happened in my project?"
```

And:

```text
git log --oneline
   ↓
Short readable history
```

```text
git log --oneline --graph --all
   ↓
Visualize history + branches
```

### One-Line Definition

> **`git log` displays the commit history of a Git repository, including information such as commit IDs, authors, dates, and commit messages.**