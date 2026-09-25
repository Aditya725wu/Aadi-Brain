# Working Directory

## What is the Working Directory?

The **Working Directory** is the actual folder where your project files are stored and where you **create, edit, and delete files**.

In simple words:

> **Working Directory = The place where you are currently working on your code.**

---

# Example

Suppose your project is:

```text
Aadi-Brain/
├── index.html
├── app.js
├── style.css
└── README.md
```

This entire project folder is your **working directory**.

When you edit:

```text
app.js
```

you are making a change in the working directory.

---

# Working Directory in Git

Git mainly deals with three important areas:

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

### Meaning

```text
Working Directory
→ Where you edit files

Staging Area
→ Where you select changes

Git Repository
→ Where committed history is stored
```

---

# Example: Editing a File

Suppose your original `app.js` contains:

```javascript
console.log("Hello");
```

You change it to:

```javascript
console.log("Hello Aditya");
```

The change is currently in the:

```text
Working Directory
```

It is **not staged yet**.

---

# How Does Git Know About the Change?

Run:

```bash
git status
```

You might see:

```text
Changes not staged for commit:
  modified: app.js
```

This means:

> `app.js` has changed in the working directory, but the change hasn't been added to the staging area.

---

# Move Changes to Staging

Use:

```bash
git add app.js
```

Now the flow becomes:

```text
Working Directory
       ↓
   git add app.js
       ↓
Staging Area
```

Check:

```bash
git status
```

You may now see:

```text
Changes to be committed:
  modified: app.js
```

---

# Working Directory vs Staging Area

Suppose you modify three files:

```text
app.js
style.css
README.md
```

Initially:

```text
Working Directory
├── app.js       modified
├── style.css    modified
└── README.md    modified
```

Then:

```bash
git add app.js
```

Now:

```text
Working Directory
├── style.css    modified
└── README.md    modified

Staging Area
└── app.js
```

So Git allows you to choose which changes should be included in the next commit.

---

# Untracked Files

A new file that Git hasn't started tracking is called an **untracked file**.

Suppose you create:

```text
login.js
```

Git may show:

```text
Untracked files:
  login.js
```

To stage it:

```bash
git add login.js
```

Now Git is preparing it for the next commit.

---

# Modified Files

If Git already knows about a file and you change it, it becomes **modified**.

Example:

```text
app.js
```

was already committed.

You edit it.

Git status:

```text
modified: app.js
```

---

# Useful Command

Always use:

```bash
git status
```

It tells you what's happening between your working directory, staging area, and repository.

---

# Working Directory Flow

```text
             EDIT
              ↓
      ┌─────────────────┐
      │ Working Directory│
      └────────┬────────┘
               │
            git add
               ↓
      ┌─────────────────┐
      │  Staging Area   │
      └────────┬────────┘
               │
          git commit
               ↓
      ┌─────────────────┐
      │ Git Repository  │
      └─────────────────┘
```

---

# Important Commands

### Check current changes

```bash
git status
```

### See unstaged changes

```bash
git diff
```

### Stage a file

```bash
git add app.js
```

### Stage everything

```bash
git add .
```

### Remove a file from staging

```bash
git restore --staged app.js
```

### Discard changes to a tracked file

```bash
git restore app.js
```

Be careful with `git restore` because it can discard uncommitted changes.

---

# Aadi Bhai Example 😎

Think about your college notebook.

You are currently writing your assignment.

```text
Your Table
   ↓
You are writing
   ↓
Working Directory
```

Then you select the pages you want to submit:

```text
Selected Pages
   ↓
Staging Area
```

Then you officially submit them:

```text
Submit
   ↓
Commit
```

So remember:

> **Working Directory = Where you work**

> **Staging Area = What you select**

> **Commit = What you save**

---

# One-Line Definition

> **The working directory is the current project folder where you create and modify files before staging and committing those changes.**