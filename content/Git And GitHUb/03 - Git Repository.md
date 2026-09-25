# Git Repository

## What is a Repository?

A **repository**, or **repo**, is a project that is managed and tracked by Git.

It contains:

- Project files
    
- Git history
    
- Commits
    
- Branch information
    
- Configuration
    
- Other Git metadata
    

---

## Simple Example

Suppose your project is:

```text
Aadi-Brain/
├── frontend/
├── backend/
├── README.md
└── package.json
```

When you run:

```bash
git init
```

Git creates a hidden `.git` folder:

```text
Aadi-Brain/
├── frontend/
├── backend/
├── README.md
├── package.json
└── .git/
```

The `.git` directory contains Git's internal repository data.

---

# Types of Repository

There are two important types to understand:

## 1. Local Repository

The repository stored on your computer.

```text
Your Computer
     ↓
Local Git Repository
```

For example:

```bash
git init
```

creates a local Git repository.

---

## 2. Remote Repository

A repository stored somewhere else, usually on a Git hosting platform such as GitHub.

```text
GitHub
   ↓
Remote Repository
```

---

# Local vs Remote

```text
        Your Computer
              |
              ↓
      Local Repository
              |
         git push
              ↓
      Remote Repository
              |
           GitHub
```

Changes can move between the local and remote repositories using Git commands.

---

# How to Create a Local Repository

Go inside your project:

```bash
cd my-project
```

Initialize Git:

```bash
git init
```

Now your project is a Git repository.

Check it:

```bash
git status
```

---

# What is `.git`?

When you run:

```bash
git init
```

Git creates:

```text
.git/
```

This is a hidden directory.

It contains information Git needs to manage the repository, including:

- Commit history
    
- Branch information
    
- Repository configuration
    
- References
    
- Objects
    

### Important

> **Do not manually modify or delete `.git` unless you understand the consequences.**

If you delete `.git`, the project files remain, but the local Git repository and its local history/configuration are removed.

---

# Repository vs Project Folder

These are not exactly the same thing.

### Project Folder

Contains your actual project files:

```text
project/
├── index.html
├── app.js
└── style.css
```

### Git Repository

A project folder that contains Git's `.git` directory:

```text
project/
├── index.html
├── app.js
├── style.css
└── .git/
```

So:

> A project folder becomes a local Git repository when Git is initialized in it.

---

# Repository and Commits

Git stores the history of your project through commits.

Example:

```text
Initial Project
      ↓
Add Navbar
      ↓
Add Login
      ↓
Fix Login Bug
```

Each commit represents a point in the repository's history.

---

# Repository and Branches

A repository can contain multiple branches.

Example:

```text
Aadi-Brain Repository
│
├── main
├── feature-login
├── feature-chatbot
└── bug-fix
```

All these branches belong to the same repository.

---

# Repository and GitHub

A local repository can be connected to a remote GitHub repository.

```text
Local Repository
       |
       | git push
       ↓
GitHub Repository
```

And changes from GitHub can be brought back:

```text
GitHub Repository
       |
       | git pull
       ↓
Local Repository
```

---

# Useful Repository Commands

## Check repository status

```bash
git status
```

## Check Git repository root

```bash
git rev-parse --show-toplevel
```

## See configured remote repositories

```bash
git remote -v
```

## View commit history

```bash
git log --oneline
```

---

# Aadi Bhai Memory Trick 😎

Think of a repository as your **project + Git history**.

```text
Project Files
      +
    .git
      ↓
Git Repository
```

And:

```text
Local Repository
      ↕
   Git Commands
      ↕
Remote Repository
      ↓
   GitHub
```

### One-line answer

> **A Git repository is a project whose files and version history are managed by Git.**