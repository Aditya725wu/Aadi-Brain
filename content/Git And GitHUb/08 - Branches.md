# Git Branches

## What is a Branch?

A **branch** is a separate development line in a Git repository.

It allows you to work on changes separately without immediately changing another branch.

### Simple Definition

> **Branch = Separate development line of your project.**

---

# Why Do We Need Branches?

Suppose your project has a stable version:

```text
main
  |
  A
  |
  B
```

Now you want to add a login feature.

Instead of making the changes directly on `main`, you can create:

```text
main
  |
  A
  |
  B
   \
    C
    |
    feature-login
```

You can work on the login feature separately.

---

# Simple Real-Life Example

Imagine your project is a road.

```text
             Feature Login
                  /
                 /
Main Road ──────●────────────
```

The `main` branch is the main road.

A feature branch is another road where you can work on something separately.

---

# Common Branches

A repository might have:

```text
main
feature-login
feature-payment
feature-dark-mode
bug-fix
```

Example:

```text
Project
│
├── main
├── feature-login
├── feature-payment
└── bug-fix
```

All of these branches belong to the same Git repository.

---

# What is `main`?

`main` is commonly used as the primary branch of a repository.

Example:

```text
main
```

It is often treated as the stable or primary development line.

However, Git itself does not require you to use `main`; a repository can use another branch name.

---

# Can I Work Directly on `main`?

### Yes. ✅

You can work directly on `main`.

For example:

```bash
git switch main
git add .
git commit -m "Add login page"
git push
```

There is no Git rule that says you must create a feature branch.

For personal projects, working directly on `main` can be perfectly reasonable.

---

# Why Use Feature Branches?

Branches become especially useful when:

- Working in a team
    
- Developing multiple features
    
- Testing experimental changes
    
- Fixing bugs
    
- Keeping the main branch stable
    
- Creating Pull Requests
    

Example:

```text
                    feature-login
                   /
main ─────────────●
                   \
                    feature-payment
```

Different work can happen independently.

---

# Create a Branch

Use:

```bash
git branch login
```

This creates a branch called:

```text
login
```

But it does **not** switch you to that branch.

---

# See Branches

Use:

```bash
git branch
```

Example:

```text
* main
  login
  payment
```

The `*` indicates the branch you are currently on.

---

# Switch to a Branch

Use:

```bash
git switch login
```

Now:

```text
  main
* login
  payment
```

You are working on `login`.

---

# Create and Switch at the Same Time

Instead of:

```bash
git branch login
git switch login
```

you can use:

```bash
git switch -c login
```

This means:

```text
Create branch
     +
Switch to branch
```

---

# Example Workflow

Start on:

```text
main
```

Create a feature branch:

```bash
git switch -c feature-login
```

Now:

```text
main
   \
    feature-login
```

Work on the feature:

```bash
git add .
git commit -m "Add login page"
```

Push the branch:

```bash
git push -u origin feature-login
```

Later, the feature can be reviewed and merged into `main`.

---

# Branches and Commits

Branches point to commits.

Example:

```text
A → B → C
         ↑
        main
```

Create a new branch:

```text
A → B → C
         ↑
        main
         \
          feature-login
```

If you create another commit on `feature-login`:

```text
A → B → C
         ↑
        main
          \
           D
           ↑
      feature-login
```

Now:

```text
main
```

still points to `C`.

The feature branch points to `D`.

---

# Important Concept

A branch does **not** usually mean that Git creates a completely separate copy of your entire project.

A branch is essentially a movable reference to a commit in Git's history.

This is why branches are lightweight and useful.

---

# Delete a Branch

After a feature is merged, you may delete the local branch:

```bash
git branch -d feature-login
```

If Git refuses because the branch hasn't been merged and you intentionally want to delete it:

```bash
git branch -D feature-login
```

Be careful with `-D`.

---

# Rename a Branch

Rename the current branch:

```bash
git branch -M main
```

For example, this is commonly used when setting the initial branch name:

```bash
git branch -M main
```

---

# Local vs Remote Branches

### Local branches

Branches on your computer:

```bash
git branch
```

### Remote-tracking branches

Branches Git knows about from a remote repository:

```bash
git branch -r
```

### All branches

```bash
git branch -a
```

---

# Branch and GitHub

A local branch can be pushed to GitHub.

Example:

```bash
git switch -c feature-login
```

Then:

```bash
git push -u origin feature-login
```

Now GitHub can have a corresponding remote branch:

```text
Local                         GitHub

feature-login  ───────────→  feature-login
```

---

# Branch vs Commit

These are different concepts.

### Commit

A saved snapshot:

```text
A → B → C
```

### Branch

A reference pointing to a commit:

```text
A → B → C
         ↑
        main
```

So:

> **Commit = Snapshot**

> **Branch = Pointer/reference to a line of development**

---

# Branch vs Repository

### Repository

The entire Git-managed project and its history.

```text
Project Repository
│
├── main
├── feature-login
├── feature-payment
└── bug-fix
```

### Branch

One development line inside that repository.

---

# Aadi Bhai Example 😎

Imagine you are building your **Aadi Brain** project.

`main` contains your working version:

```text
main
 |
 A
 |
 B
```

Now you want to add a chatbot.

Create:

```bash
git switch -c feature-chatbot
```

Now:

```text
main
 |
 A
 |
 B
  \
   C
   ↑
feature-chatbot
```

You work on the chatbot:

```bash
git add .
git commit -m "Add chatbot"
```

Now:

```text
main
 |
 A
 |
 B

feature-chatbot
 |
 C
```

Later, you can merge the chatbot changes into `main`.

---

# Most Important Branch Commands

```bash
# See branches
git branch

# Create branch
git branch feature-login

# Switch branch
git switch feature-login

# Create + switch
git switch -c feature-login

# Delete branch
git branch -d feature-login

# Force delete branch
git branch -D feature-login

# Rename current branch
git branch -M main

# See remote branches
git branch -r

# See all branches
git branch -a
```

---

# Aadi Bhai Memory Trick

Remember:

```text
git branch
      ↓
See / create branches

git switch
      ↓
Move between branches

git switch -c
      ↓
Create + move

git merge
      ↓
Combine branches
```

### One-Line Definition

> **A Git branch is a lightweight development line that allows you to work on changes independently within the same repository.**