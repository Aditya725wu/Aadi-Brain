# Git Pull

## What is `git pull`?

`git pull` is used to **get changes from a remote repository and integrate them into your current local branch**.

### Simple Definition

> **`git pull` = Get the latest changes from GitHub and bring them into my local branch.**

---

# Basic Flow

```text
GitHub / Remote Repository
          ↓
       git pull
          ↓
   Local Repository
```

---

# Why Do We Need `git pull`?

Imagine you and your friend are working on the same project.

Your friend pushes a new commit to GitHub:

```text
GitHub:
A → B → C
```

But your computer has:

```text
Local:
A → B
```

Your local repository is behind.

You can use:

```bash
git pull
```

Now your local repository can receive the remote changes.

```text
Local:
A → B → C
```

---

# Basic Command

```bash
git pull
```

If your current branch has an upstream branch configured, Git knows which remote branch to pull from.

---

# Explicit Pull

You can specify the remote and branch:

```bash
git pull origin main
```

Breakdown:

```text
git pull
   ↓
Get and integrate changes

origin
   ↓
Remote name

main
   ↓
Remote branch
```

---

# Typical Workflow

Before starting work:

```bash
git switch main
git pull
```

Then work on your code:

```bash
git add .
git commit -m "Add login feature"
git push
```

So a common workflow is:

```text
Pull
 ↓
Work
 ↓
Add
 ↓
Commit
 ↓
Push
```

---

# `git pull` and `git fetch`

This is very important.

Conceptually:

```text
git pull
   =
git fetch
   +
integration
```

### `git fetch`

Downloads information from the remote without automatically integrating it into your current branch.

```bash
git fetch
```

### `git pull`

Fetches the remote changes and then integrates them into the current branch according to Git's configured pull behavior.

```bash
git pull
```

---

# Example

Suppose GitHub has:

```text
A → B → C
```

Your local branch has:

```text
A → B
```

Run:

```bash
git pull
```

Git retrieves the remote changes and integrates them.

Your local branch may then become:

```text
A → B → C
```

The exact result can differ if both local and remote branches have diverged.

---

# What if Both Local and Remote Have Changes?

Suppose:

```text
Local:
A → B → D

Remote:
A → B → C
```

Now the branches have **diverged**.

```text
        D  ← Local
       /
A → B
       \
        C  ← Remote
```

Running:

```bash
git pull
```

may require Git to reconcile the two histories.

Depending on your configuration and situation, Git may:

- Merge the histories
    
- Rebase your local commits
    
- Stop and ask you to resolve a conflict
    

---

# Pull Conflicts

A conflict can happen when local and remote changes overlap in a way Git cannot automatically reconcile.

Example:

```text
Local:
console.log("Hello");

Remote:
console.log("Hello World");
```

Both changes affect the same part of the file.

Git may mark a conflict like:

```text
<<<<<<< HEAD
console.log("Hello");
=======
console.log("Hello World");
>>>>>>> origin/main
```

You need to decide what the final code should be.

After resolving the conflict:

```bash
git add <resolved-file>
```

Then complete the required merge or rebase operation according to what Git requested.

---

# Important: `git pull` Does Not Mean "Download Files Only"

A common misunderstanding is:

```text
git pull = download
```

More accurately:

> `git pull` fetches remote changes and integrates them into your current branch.

If you only want to download remote information without integrating it:

```bash
git fetch
```

---

# Pull Before Starting Work

In a shared project, a common habit is:

```bash
git switch main
git pull
```

This helps you start from the latest remote state.

Then:

```bash
git switch -c feature-login
```

Work on the feature:

```bash
git add .
git commit -m "Add login feature"
```

Push:

```bash
git push -u origin feature-login
```

---

# Pull vs Push

These are opposites in direction, but they are not exact mirror operations.

## Push

```bash
git push
```

```text
Local
  ↓
Remote
```

You send your local commits to the remote repository.

## Pull

```bash
git pull
```

```text
Remote
  ↓
Local
```

You retrieve remote changes and integrate them into your current branch.

---

# Pull vs Fetch

|Command|What it does|
|---|---|
|`git fetch`|Downloads remote information without automatically integrating it|
|`git pull`|Fetches and integrates remote changes|

---

# Aadi Bhai Example 😎

Imagine you and your friend are editing the same Google-like project.

Your friend adds:

```text
Login page
```

and pushes it to GitHub.

Your laptop doesn't have that change yet.

You run:

```bash
git pull
```

Git gets the remote changes and integrates them into your local branch.

Think:

```text
Friend
  ↓
GitHub
  ↓
git pull
  ↓
Your Computer
```

---

# Common Commands

```bash
# Pull current branch
git pull

# Pull a specific remote branch
git pull origin main

# Fetch without integrating
git fetch

# Check current branch
git branch

# Check repository state
git status
```

---

# Safe Habit Before Pulling

If you have important uncommitted changes, check:

```bash
git status
```

If necessary, save your work first with a commit or stash.

For example:

```bash
git stash
git pull
git stash pop
```

But only use this when you understand how the local changes interact with the incoming changes.

---

# Aadi Bhai Memory Trick

Remember:

```text
git push
    ↓
LOCAL → GITHUB
```

```text
git pull
    ↓
GITHUB → LOCAL
```

And:

```text
git fetch
    ↓
Get remote information
without automatically integrating it
```

### One-Line Definition

> **`git pull` fetches changes from a remote repository and integrates them into your current local branch.**