# Git Status

## What is `git status`?

`git status` is a Git command that shows the **current state of your working directory and staging area**.

### Simple Definition

> **`git status` = "Git, tell me what is happening in my project right now."**

---

# Basic Command

```bash
git status
```

You can run it anytime.

It is one of the most useful Git commands.

---

# What Does `git status` Show?

It can tell you:

- Which branch you are currently on
    
- Which files are modified
    
- Which files are staged
    
- Which files are untracked
    
- Which changes are ready to commit
    
- Whether your local branch is ahead or behind its remote branch
    

---

# Example 1 — Clean Repository

Suppose everything has been committed.

Run:

```bash
git status
```

You may see something like:

```text
On branch main
nothing to commit, working tree clean
```

This means:

```text
No uncommitted changes
        ↓
Everything is clean
```

---

# Example 2 — Modified File

Suppose you edit:

```text
app.js
```

Then:

```bash
git status
```

may show:

```text
Changes not staged for commit:
  modified: app.js
```

This means:

```text
app.js
   ↓
Modified
   ↓
Not staged yet
```

You can stage it:

```bash
git add app.js
```

---

# Example 3 — Staged File

After:

```bash
git add app.js
```

run:

```bash
git status
```

You may see:

```text
Changes to be committed:
  modified: app.js
```

This means:

```text
app.js
   ↓
Staged
   ↓
Ready for commit
```

Now:

```bash
git commit -m "Update app logic"
```

---

# Example 4 — Untracked File

Suppose you create a new file:

```text
login.js
```

Git may show:

```text
Untracked files:
  login.js
```

This means Git has not yet started tracking that file.

To stage it:

```bash
git add login.js
```

---

# Three Important States

A file can commonly appear in these states:

```text
Untracked
    ↓
Modified
    ↓
Staged
    ↓
Committed
```

More accurately, these describe different relationships between your working tree, index/staging area, and committed snapshot.

---

# Complete Example

Suppose your project contains:

```text
app.js
style.css
login.js
```

You modify:

```text
app.js
style.css
```

and create:

```text
login.js
```

Run:

```bash
git status
```

You may see:

```text
Changes not staged for commit:
  modified: app.js
  modified: style.css

Untracked files:
  login.js
```

Now stage only:

```bash
git add app.js
```

Run:

```bash
git status
```

You may now see:

```text
Changes to be committed:
  modified: app.js

Changes not staged for commit:
  modified: style.css

Untracked files:
  login.js
```

This tells you exactly what will happen if you commit now.

---

# Status After Commit

Suppose you run:

```bash
git commit -m "Update app"
```

Then:

```bash
git status
```

may show:

```text
Changes not staged for commit:
  modified: style.css

Untracked files:
  login.js
```

Why?

Because only `app.js` was staged and committed.

---

# Status and Branch

`git status` also tells you your current branch.

Example:

```text
On branch feature-login
```

This is important before making commits.

You can quickly check:

```bash
git status
```

instead of separately running:

```bash
git branch
```

---

# Status and Remote

If your branch is connected to a remote branch, `git status` can also tell you whether your local branch is ahead or behind.

Example:

```text
Your branch is ahead of 'origin/main' by 2 commits.
```

This means:

```text
Local:
A → B → C → D

Remote:
A → B
```

You can send those commits using:

```bash
git push
```

---

# Ahead and Behind

### Ahead

Your local branch has commits that the remote doesn't have.

```text
Local:
A → B → C

Remote:
A → B
```

You are ahead.

Usually:

```bash
git push
```

can send those commits.

---

### Behind

The remote has commits that your local branch doesn't have.

```text
Local:
A → B

Remote:
A → B → C
```

You are behind.

You may need:

```bash
git pull
```

or a fetch-and-integrate workflow.

---

# `git status` vs `git diff`

These commands have different purposes.

### `git status`

Tells you **what state files are in**.

```bash
git status
```

### `git diff`

Shows **the actual content changes**.

```bash
git diff
```

Example:

```text
git status
→ app.js is modified

git diff
→ Shows exactly what changed in app.js
```

---

# `git status` vs `git log`

### `git status`

Shows the **current state**.

```bash
git status
```

### `git log`

Shows the **commit history**.

```bash
git log
```

Think:

```text
status → What is happening now?

log → What happened before?
```

---

# Useful Status Command

For a shorter output:

```bash
git status --short
```

Example:

```text
 M app.js
M  style.css
?? login.js
```

Common meanings:

```text
 M → Modified in working directory
M  → Staged modification
?? → Untracked file
```

The two-column format represents the state in the staging area and working tree.

---

# Typical Workflow Using `git status`

A good habit is:

```bash
git status
```

Then:

```bash
git add .
```

Then:

```bash
git status
```

Then:

```bash
git commit -m "Add feature"
```

Then:

```bash
git status
```

Then:

```bash
git push
```

---

# Aadi Bhai Example 😎

Think of `git status` as asking your project:

> **"Bhai, abhi kya scene hai?" 😂**

Git answers:

```text
You are on main.

app.js → modified
style.css → staged
login.js → untracked

2 commits ahead of origin/main.
```

Now you know exactly what is happening.

---

# Aadi Bhai Memory Trick

```text
git status
     ↓
Current Git situation
     ↓
Branch?
Modified files?
Staged files?
Untracked files?
Ahead/behind?
```

### One-Line Definition

> **`git status` displays the current state of your Git working directory, staging area, branch, and relevant remote-tracking relationship.**