# Origin

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