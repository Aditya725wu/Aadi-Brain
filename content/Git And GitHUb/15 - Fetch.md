# Git Fetch

## What is `git fetch`?

`git fetch` is used to **download information about changes from a remote repository without automatically integrating those changes into your current branch**.

### Simple Definition

> **`git fetch` = Get information about what's changed on GitHub, but don't merge it into my current work yet.**

---

# Basic Flow

```text
GitHub / Remote
      ↓
  git fetch
      ↓
Remote-tracking information
```

Your current working files are not automatically changed by the fetched commits.

---

# Why Use `git fetch`?

Suppose your local repository has:

```text
A → B
```

But GitHub has:

```text
A → B → C → D
```

You want to know what changed on GitHub **before integrating those changes**.

Run:

```bash
git fetch
```

Git downloads information about `C` and `D`.

You can then inspect the remote-tracking branch before deciding what to do.

---

# `git fetch` Does Not Automatically Merge

This is the main difference from `git pull`.

```text
git fetch
    ↓
Download remote changes
    ↓
Do NOT automatically integrate
```

Whereas:

```text
git pull
    ↓
Fetch
    ↓
Integrate
```

---

# Fetch Example

Suppose:

```text
Local main:
A → B

Remote main:
A → B → C
```

Run:

```bash
git fetch origin
```

Now Git knows about the remote commit `C`.

You may see:

```text
main
  ↓
  B

origin/main
  ↓
  C
```

Your local `main` branch itself has not automatically moved to `C`.

---

# What is `origin/main`?

This is important.

```text
origin/main
```

is a **remote-tracking branch**.

It represents Git's local record of where the remote `main` branch was the last time Git updated its remote-tracking information.

For example:

```text
main
  ↓
  B

origin/main
  ↓
  C
```

This means:

- Your local `main` is at `B`
    
- Git knows that the remote `main` is at `C`
    

---

# Fetch From a Specific Remote

```bash
git fetch origin
```

Here:

```text
origin
   ↓
Remote name
```

---

# Fetch a Specific Branch

You can fetch a specific branch:

```bash
git fetch origin main
```

This updates your remote-tracking information for that branch.

---

# Fetch All Remotes

If you have multiple remotes:

```bash
git fetch --all
```

This fetches from all configured remotes.

---

# Fetch and Inspect Changes

Suppose:

```text
Local:
A → B

Remote:
A → B → C → D
```

First:

```bash
git fetch origin
```

Then compare:

```bash
git log main..origin/main --oneline
```

This can show commits that are on the remote-tracking branch but not on your local `main`.

You can also inspect differences with:

```bash
git diff main origin/main
```

---

# Fetch vs Pull

This is one of the most important Git differences.

|Command|Action|
|---|---|
|`git fetch`|Download remote information without automatically integrating it|
|`git pull`|Fetch and integrate remote changes|

### Visual

```text
             GitHub
                │
        ┌───────┴───────┐
        ↓               ↓
   git fetch        git pull
        ↓               ↓
Remote information   Integrate changes
        ↓               ↓
You inspect        Current branch changes
```

---

# Fetch vs Push

These work in opposite directions.

### Fetch

```text
Remote
  ↓
Local Git information
```

```bash
git fetch
```

### Push

```text
Local
  ↓
Remote
```

```bash
git push
```

---

# Fetch Does Not Change Your Working Files Automatically

Suppose you're currently editing:

```text
app.js
```

You run:

```bash
git fetch
```

Git doesn't automatically replace your working file with the remote version.

That's one reason `fetch` is useful when you want to inspect incoming changes before integrating them.

---

# Typical Team Workflow

Suppose you are working on `main`.

First:

```bash
git fetch origin
```

Check whether remote has new commits:

```bash
git log main..origin/main --oneline
```

If you decide to integrate the changes, you can then use an appropriate workflow such as:

```bash
git merge origin/main
```

or:

```bash
git pull
```

The exact choice depends on your team's workflow.

---

# Example With Branches

Suppose GitHub has:

```text
origin/main
origin/feature-login
```

You can fetch:

```bash
git fetch origin
```

Then Git updates its knowledge of those remote branches.

You can see remote-tracking branches with:

```bash
git branch -r
```

Example:

```text
origin/main
origin/feature-login
```

---

# Important Commands

### Fetch from default remote

```bash
git fetch
```

### Fetch from `origin`

```bash
git fetch origin
```

### Fetch a specific branch

```bash
git fetch origin main
```

### Fetch all remotes

```bash
git fetch --all
```

### See remote branches

```bash
git branch -r
```

### Compare local and remote

```bash
git log main..origin/main --oneline
```

```bash
git diff main origin/main
```

---

# Aadi Bhai Example 😎

Imagine your friend is working on the same project.

Your computer:

```text
A → B
```

Friend pushes:

```text
A → B → C → D
```

You don't want to immediately bring those changes into your branch.

You first ask Git:

> "Hey, tell me what's new."

```bash
git fetch
```

Now Git knows about:

```text
C
D
```

You can inspect them.

If everything looks good, you can integrate them.

---

# A Simple Analogy

Think of `git fetch` like checking your mailbox.

```text
Mail arrives
    ↓
You check it
    ↓
You read it
    ↓
You decide what to do
```

`git fetch`:

```text
Remote changes arrive
        ↓
Git downloads information
        ↓
You inspect
        ↓
You decide whether/how to integrate
```

---

# Aadi Bhai Memory Trick

Remember these three:

```text
git push
   ↓
LOCAL → REMOTE
```

```text
git fetch
   ↓
REMOTE → Download information
   ↓
No automatic integration
```

```text
git pull
   ↓
REMOTE → LOCAL
   ↓
Fetch + Integrate
```

### One-Line Definition

> **`git fetch` downloads updates from a remote repository and updates your remote-tracking information without automatically integrating those changes into your current branch.**