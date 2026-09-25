# Git Push

## What is `git push`?

`git push` is used to **send your local commits to a remote repository** such as GitHub.

### Simple Definition

> **`git push` = Send my local commits to GitHub.**

---

# Basic Flow

```text
Your Code
   ↓
git add
   ↓
Staging Area
   ↓
git commit
   ↓
Local Repository
   ↓
git push
   ↓
GitHub / Remote Repository
```

---

# Important: Push Does NOT Directly Upload Every File

This is important.

When you run:

```bash
git push
```

Git pushes **commits**, not simply every file in your working directory.

You normally need:

```text
Edit
 ↓
git add
 ↓
git commit
 ↓
git push
```

---

# Basic Command

```bash
git push
```

If your local branch already has an upstream branch configured, this is usually enough.

---

# First Push

When pushing a branch for the first time, you commonly use:

```bash
git push -u origin main
```

Breakdown:

```text
git push
   ↓
Push commits

origin
   ↓
Remote name

main
   ↓
Branch name
```

The `-u` sets the upstream/tracking relationship.

After that, you can usually use:

```bash
git push
```

---

# Complete Example

Suppose you created a project.

### Step 1 — Initialize Git

```bash
git init
```

### Step 2 — Stage files

```bash
git add .
```

### Step 3 — Create commit

```bash
git commit -m "Initial commit"
```

### Step 4 — Connect GitHub repository

```bash
git remote add origin <github-url>
```

### Step 5 — Make sure branch is `main`

```bash
git branch -M main
```

### Step 6 — Push

```bash
git push -u origin main
```

Now your commit is available in the remote repository.

---

# What Happens During Push?

Suppose your local history is:

```text
Local:

A → B → C
```

But GitHub currently has:

```text
GitHub:

A → B
```

You run:

```bash
git push
```

After the push:

```text
Local:

A → B → C

GitHub:

A → B → C
```

The remote repository now has the commits that were pushed.

---

# Push a Feature Branch

Suppose you create:

```bash
git switch -c feature-login
```

Make changes:

```bash
git add .
git commit -m "Add login feature"
```

Push the branch:

```bash
git push -u origin feature-login
```

Now GitHub has the branch:

```text
GitHub
│
├── main
└── feature-login
```

---

# Push to a Specific Remote Branch

General syntax:

```bash
git push <remote> <branch>
```

Example:

```bash
git push origin main
```

Another example:

```bash
git push origin feature-login
```

---

# Check Remote Before Pushing

Use:

```bash
git remote -v
```

Example:

```text
origin  https://github.com/username/project.git (fetch)
origin  https://github.com/username/project.git (push)
```

This lets you verify where you're pushing.

---

# Check Your Current Branch

Before pushing, you can use:

```bash
git branch
```

Example:

```text
* main
  feature-login
```

The `*` shows your current branch.

---

# Push vs Commit

These are different.

## `git commit`

```bash
git commit -m "Add login"
```

Saves the staged changes in your **local Git history**.

```text
Working Directory
       ↓
Staging
       ↓
Local Repository
```

## `git push`

```bash
git push
```

Sends your local commits to the **remote repository**.

```text
Local Repository
       ↓
    git push
       ↓
Remote Repository
```

---

# Push vs Add

### `git add`

```bash
git add .
```

Selects changes for the next commit.

### `git commit`

```bash
git commit -m "message"
```

Saves those staged changes locally.

### `git push`

```bash
git push
```

Sends those commits to the remote.

Remember:

```text
git add
   ↓
SELECT

git commit
   ↓
SAVE LOCALLY

git push
   ↓
SEND TO REMOTE
```

---

# Common Push Error

You may sometimes see:

```text
! [rejected] main -> main (fetch first)
```

This generally means the remote branch has commits that your local branch does not have.

For example:

```text
Local:
A → B

GitHub:
A → B → C
```

Your local repository is behind the remote.

A common next step is:

```bash
git pull
```

Then resolve any conflicts if necessary, commit if needed, and push again.

```bash
git push
```

### Important

Don't blindly use force push to solve every push rejection.

---

# Force Push

You may see:

```bash
git push --force
```

or:

```bash
git push -f
```

This can overwrite remote branch history.

It should be used carefully, especially on shared branches.

A safer option in many situations is:

```bash
git push --force-with-lease
```

But even that should be used only when you understand the history you are rewriting.

---

# Push a New Branch

Example:

```bash
git switch -c feature-chatbot

git add .
git commit -m "Add chatbot"

git push -u origin feature-chatbot
```

After pushing:

```text
Local
  |
  └── feature-chatbot
          ↓
       GitHub
          |
          └── feature-chatbot
```

---

# Aadi Bhai Example 😎

Imagine you wrote an assignment on your laptop.

```text
Laptop
  ↓
You finish assignment
  ↓
Save it
  ↓
Send it to teacher
```

Git equivalent:

```text
Laptop
  ↓
git commit
  ↓
Local Repository
  ↓
git push
  ↓
GitHub
```

So:

> **Commit = Save locally**

> **Push = Send the saved commits to the remote**

---

# Daily Push Workflow

For a simple personal project:

```bash
git status

git add .

git commit -m "Update project"

git push
```

For a feature branch:

```bash
git status

git add .

git commit -m "Add login feature"

git push -u origin feature-login
```

After the first push of that branch:

```bash
git push
```

is usually enough.

---

# Most Important Commands

```bash
# Push current branch
git push

# First push of main
git push -u origin main

# Push a feature branch
git push -u origin feature-login

# Check remote
git remote -v

# Check current branch
git branch
```

---

# Aadi Bhai Memory Trick

```text
git add
   ↓
Select changes

git commit
   ↓
Save locally

git push
   ↓
Send commits to GitHub
```

### One-Line Definition

> **`git push` transfers your local commits to a remote repository such as GitHub.**# Origin

## What is `origin`?

`origin` is the **default/conventional name** given to a remote repository when you connect your local Git repository to a remote repository.

For example:

```bash
git remote add origin <github-url>
```

Here:

```text
origin
   ↓
Name of the remote
```

It points to the remote repository URL.

---

# Simple Meaning

Think of `origin` as a **nickname**.

Instead of typing the entire GitHub URL every time:

```text
https://github.com/username/project.git
```

you can simply say:

```text
origin
```

So:

```bash
git push origin main
```

means:

> Push the `main` branch to the remote repository named `origin`.

---

# How is `origin` Created?

Suppose you already have a local Git repository:

```bash
git init
```

Then you connect it to GitHub:

```bash
git remote add origin https://github.com/username/project.git
```

Now Git remembers:

```text
origin → https://github.com/username/project.git
```

---

# Check `origin`

Use:

```bash
git remote -v
```

Example:

```text
origin  https://github.com/username/project.git (fetch)
origin  https://github.com/username/project.git (push)
```

This means `origin` is configured for both fetching and pushing.

---

# `origin` Is Not GitHub

This is important.

```text
GitHub
   ↓
Online platform
```

While:

```text
origin
   ↓
Name/alias for a remote
```

For example:

```text
origin
   ↓
https://github.com/username/project.git
```

So **origin is just a name**, not a special GitHub feature.

---

# Can We Use Another Name?

Yes.

You don't have to call the remote `origin`.

For example:

```bash
git remote add github <url>
```

Now the remote is named:

```text
github
```

You could then use:

```bash
git push github main
```

However, `origin` is the most common convention for the primary remote.

---

# `origin` and `git push`

You can specify the remote explicitly:

```bash
git push origin main
```

Break it down:

```text
git push
   ↓
Operation: send commits

origin
   ↓
Which remote?

main
   ↓
Which branch?
```

So:

```bash
git push origin main
```

means:

> Send the local `main` branch to the remote named `origin`.

---

# `origin` and `git pull`

You can also specify the remote and branch:

```bash
git pull origin main
```

Meaning:

> Get changes from the `main` branch of the remote named `origin` and integrate them into the current branch.

---

# `origin` and `git fetch`

Similarly:

```bash
git fetch origin
```

means:

> Fetch information from the remote named `origin`.

---

# `origin` and `-u`

The first time you push a branch, you might use:

```bash
git push -u origin main
```

The `-u` establishes an **upstream/tracking relationship** between your local branch and the remote branch.

After that, you can often simply use:

```bash
git push
```

and:

```bash
git pull
```

because Git knows the default remote branch to use.

---

# Example From Start to Finish

## Step 1 — Create Git repository

```bash
git init
```

## Step 2 — Add files

```bash
git add .
```

## Step 3 — Commit

```bash
git commit -m "Initial commit"
```

## Step 4 — Add remote

```bash
git remote add origin <github-url>
```

Now:

```text
Local Repository
       |
       | origin
       ↓
Remote GitHub Repository
```

## Step 5 — Push

```bash
git push -u origin main
```

---

# Change the `origin` URL

If the GitHub repository URL changes, you can update it:

```bash
git remote set-url origin <new-url>
```

Check:

```bash
git remote -v
```

---

# Remove `origin`

If you no longer want that remote:

```bash
git remote remove origin
```

This removes the remote configuration from your local repository.

It does **not** delete the repository from GitHub.

---

# Multiple Remotes

A repository can have multiple remotes.

Example:

```text
origin
upstream
```

You can see them:

```bash
git remote -v
```

Example:

```text
origin    <url-1>
upstream  <url-2>
```

This is common when working with forks.

---

# Aadi Bhai Example 😎

Imagine your friend has your GitHub project.

Instead of remembering their full address:

```text
"Hey, go to this long address..."
```

you give it a nickname:

```text
origin
```

Now:

```bash
git push origin main
```

means:

> "Git, send my main branch to the remote I call `origin`."

---

# Important Commands

```bash
# Add origin
git remote add origin <url>

# See origin
git remote -v

# Push to origin
git push origin main

# Pull from origin
git pull origin main

# Fetch from origin
git fetch origin

# Change origin URL
git remote set-url origin <new-url>

# Remove origin
git remote remove origin
```

---

# Aadi Bhai Memory Trick

Remember:

```text
origin = nickname of a remote repository
```

Example:

```text
origin
   ↓
GitHub Repository
```

And:

```bash
git push origin main
```

Breakdown:

```text
push  → send changes
origin → which remote
main  → which branch
```

### One-Line Definition

> **`origin` is the conventional name (alias) for a remote repository, commonly the GitHub repository connected to your local Git repository.**