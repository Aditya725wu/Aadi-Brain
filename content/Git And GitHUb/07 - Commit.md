# Git Commit

## What is a Commit?

A **commit** is a saved snapshot of the staged changes in your Git repository.

In simple words:

> **Commit = Save point of your project.**

Think of a video game:

```text
Play Game
   ↓
Reach Level
   ↓
Save Game
```

In Git:

```text
Write Code
   ↓
git add
   ↓
git commit
```

A commit creates a point in your project's history that you can refer back to later.

---

# Basic Git Flow

```text
Working Directory
       ↓
    git add
       ↓
Staging Area
       ↓
   git commit
       ↓
Local Repository
```

So remember:

```text
git add    → Select changes
git commit → Save selected changes
```

---

# Basic Commit Command

```bash
git commit -m "Add login page"
```

Here:

```text
git commit
```

means:

> Create a new commit.

And:

```text
-m
```

means:

> Provide the commit message directly.

Then:

```text
"Add login page"
```

describes what changed.

---

# Simple Example

Suppose your project contains:

```text
project/
├── index.html
├── app.js
└── style.css
```

You modify:

```text
app.js
```

Check:

```bash
git status
```

Git may show:

```text
modified: app.js
```

Now stage it:

```bash
git add app.js
```

Then commit:

```bash
git commit -m "Update application logic"
```

Now that staged version of `app.js` is part of your Git history.

---

# What Exactly Gets Committed?

This is very important.

`git commit` saves the **staged changes**.

Suppose:

```text
app.js       → staged
style.css    → modified but NOT staged
```

Then you run:

```bash
git commit -m "Update app"
```

The commit includes the staged `app.js` changes.

The unstaged `style.css` changes are not included.

---

# Why Do We Need Commit Messages?

Imagine your history looks like:

```text
Commit 1 → Initial project
Commit 2 → Add navbar
Commit 3 → Add login page
Commit 4 → Fix login validation
Commit 5 → Add dashboard
```

You can easily understand what happened.

Bad history:

```text
Commit 1 → abc
Commit 2 → changes
Commit 3 → done
Commit 4 → final
```

This tells you almost nothing.

---

# Good Commit Messages

Use clear messages.

```bash
git commit -m "Add login page"
```

```bash
git commit -m "Fix navbar alignment"
```

```bash
git commit -m "Add user authentication"
```

```bash
git commit -m "Fix login validation bug"
```

---

# Bad Commit Messages

Avoid:

```bash
git commit -m "changes"
```

```bash
git commit -m "abc"
```

```bash
git commit -m "done"
```

```bash
git commit -m "final final"
```

---

# Commit History

Every commit becomes part of your repository history.

Example:

```text
A → B → C → D
```

Where:

```text
A = Initial project
B = Add navbar
C = Add login
D = Fix login bug
```

---

# Every Commit Has an ID

Git gives every commit a unique hash.

Example:

```text
a82f321 Add login
c71ab92 Add navbar
b52cd11 Initial commit
```

These values:

```text
a82f321
c71ab92
b52cd11
```

are shortened versions of commit hashes.

Git uses commit hashes to identify commits.

---

# View Commit History

Use:

```bash
git log
```

You may see:

```text
commit a82f321...
Author: Aditya
Date: ...

    Add login page
```

---

# Short Commit History

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

This is easier to read.

---

# View Branch History Graph

Use:

```bash
git log --oneline --graph --all
```

Example:

```text
* a82f321 Add login
* c71ab92 Add navbar
* b52cd11 Initial commit
```

This becomes more useful when you start working with branches.

---

# Commit vs Push

Do not confuse these.

## Commit

```bash
git commit -m "Add login"
```

Saves changes in your **local Git repository**.

```text
Your Computer
     ↓
Local Repository
```

## Push

```bash
git push
```

Sends local commits to a **remote repository**, such as GitHub.

```text
Local Repository
       ↓
    git push
       ↓
GitHub
```

---

# Important

You can make many commits without internet.

For example:

```bash
git commit -m "Add navbar"
git commit -m "Add login"
git commit -m "Add dashboard"
```

These commits exist locally.

Later:

```bash
git push
```

You can send the commits to the remote repository.

---

# Commit vs Save File

Pressing:

```text
Ctrl + S
```

saves the file on your computer.

But it does **not** create a Git commit.

Example:

```text
Ctrl + S
   ↓
Save file

git add .
   ↓
Stage changes

git commit
   ↓
Save snapshot in Git history
```

These are different operations.

---

# Complete Example

Modify:

```text
app.js
```

Check:

```bash
git status
```

Stage:

```bash
git add app.js
```

Check again:

```bash
git status
```

Commit:

```bash
git commit -m "Update app logic"
```

View history:

```bash
git log --oneline
```

Then, if you want to send the commit to GitHub:

```bash
git push
```

---

# Aadi Bhai Memory Trick 😎

Imagine you're playing GTA.

You make progress:

```text
Play
 ↓
Complete Mission
 ↓
Save Game
```

Git is similar:

```text
Code
 ↓
git add
 ↓
Select Changes
 ↓
git commit
 ↓
Create Save Point
```

Then:

```text
Save Point
   ↓
git push
   ↓
GitHub
```

---

# Golden Rule

Remember:

```text
EDIT
 ↓
git add
 ↓
STAGE
 ↓
git commit
 ↓
SAVE IN GIT HISTORY
 ↓
git push
 ↓
SEND TO GITHUB
```

## One-Line Definition

> **A Git commit is a saved snapshot of staged changes in the repository's history.**