# Git Staging Area

## What is the Staging Area?

The **Staging Area** is the place where you select which changes should be included in your **next commit**.

Think of it as a **selection box**.

You modify files first, then use `git add` to select the changes you want to commit.

---

# Git Flow

```text
Working Directory
       ↓
     git add
       ↓
 Staging Area
       ↓
   git commit
       ↓
Git Repository
```

This is one of the most important Git concepts.

---

# Simple Example

Suppose your project contains:

```text
project/
├── app.js
├── style.css
└── README.md
```

You modify all three files.

Git sees:

```text
app.js       → modified
style.css   → modified
README.md   → modified
```

But suppose you only want to commit `app.js`.

You run:

```bash
git add app.js
```

Now:

```text
Working Directory
├── style.css
├── README.md
└── app.js

        ↓

Staging Area
└── app.js
```

Only `app.js` is prepared for the next commit.

---

# Why Do We Need Staging?

Suppose you made changes to:

```text
login.js
payment.js
navbar.js
```

But your login feature is ready and payment is still incomplete.

You can stage only:

```bash
git add login.js
```

Then commit:

```bash
git commit -m "Add login feature"
```

Your unfinished payment changes remain in your working directory.

This allows you to create **clean, focused commits**.

---

# `git add`

`git add` moves changes into the staging area.

### Add one file

```bash
git add app.js
```

### Add multiple files

```bash
git add app.js style.css
```

### Add everything

```bash
git add .
```

---

# Check Staging Status

Use:

```bash
git status
```

Example:

```text
Changes to be committed:
  modified: app.js

Changes not staged for commit:
  modified: style.css
```

This means:

```text
app.js
   ↓
Staged

style.css
   ↓
Modified but not staged
```

---

# See Staged Changes

Use:

```bash
git diff --staged
```

This shows the changes currently waiting for the next commit.

---

# Remove a File From Staging

Suppose you ran:

```bash
git add .
```

But you don't want `style.css` in the next commit.

Use:

```bash
git restore --staged style.css
```

Now:

```text
Staging Area
     ↓
style.css removed from staging
     ↓
Working Directory
```

Your changes to `style.css` are normally still there.

---

# Important Difference

### `git add`

```bash
git add app.js
```

Means:

> "Prepare the current changes in `app.js` for my next commit."

### `git commit`

```bash
git commit -m "Update app"
```

Means:

> "Save the staged changes as a commit."

---

# Complete Example

Suppose you modify:

```text
app.js
style.css
README.md
```

Check:

```bash
git status
```

Stage only `app.js`:

```bash
git add app.js
```

Check again:

```bash
git status
```

Review:

```bash
git diff --staged
```

Commit:

```bash
git commit -m "Update application logic"
```

Now the commit contains the staged `app.js` changes.

---

# Three Important Areas

Git can be understood using three main areas:

```text
┌─────────────────────┐
│  Working Directory  │
│                     │
│  You modify files   │
└──────────┬──────────┘
           │
        git add
           ↓
┌─────────────────────┐
│    Staging Area     │
│                     │
│  Select changes     │
└──────────┬──────────┘
           │
       git commit
           ↓
┌─────────────────────┐
│  Git Repository      │
│                     │
│  Saved history       │
└─────────────────────┘
```

---

# Aadi Bhai Example 😎

Imagine you're submitting a college assignment.

You have:

```text
Assignment
Notes
Random Work
```

You don't want to submit everything.

So you select only:

```text
Assignment
```

That selection step is similar to **staging**.

```text
All Work
   ↓
Select What You Want
   ↓
Staging
   ↓
Submit
   ↓
Commit
```

---

# Most Important Commands

```bash
# Check status
git status

# Stage one file
git add file.txt

# Stage everything
git add .

# See staged changes
git diff --staged

# Remove from staging
git restore --staged file.txt

# Save staged changes
git commit -m "Your message"
```

---

# Remember

> **Working Directory = Where you work**

> **Staging Area = What you select**

> **Commit = What you save**

### The Golden Flow

```text
EDIT
 ↓
git add
 ↓
STAGE
 ↓
git commit
 ↓
SAVE
```