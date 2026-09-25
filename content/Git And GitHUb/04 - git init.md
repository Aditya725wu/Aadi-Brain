# Git Init

## What is `git init`?

`git init` is used to **initialize a Git repository** inside a folder.

```bash
git init
```

It tells Git:

> **"Start tracking this project with Git."**

---

## Example

Suppose you have a project:

```text
Aadi-Brain/
├── frontend/
├── backend/
├── README.md
└── package.json
```

Go inside the project:

```bash
cd Aadi-Brain
```

Then run:

```bash
git init
```

Git initializes the project.

---

## What Happens After `git init`?

Git creates a hidden folder called:

```text
.git
```

Your project becomes:

```text
Aadi-Brain/
├── frontend/
├── backend/
├── README.md
├── package.json
└── .git/
```

The `.git` directory contains Git's internal information, including repository history and configuration.

---

# What Does `git init` Do?

`git init`:

- Initializes a local Git repository
    
- Creates the `.git` directory
    
- Allows Git to track changes
    
- Enables commits
    
- Enables branches
    
- Starts version control for the folder
    

---

# What Does `git init` NOT Do?

This is very important.

`git init` does **NOT**:

- Create a GitHub repository
    
- Upload your code
    
- Create a commit
    
- Push your code
    
- Automatically connect your project to GitHub
    

For example:

```bash
git init
```

doesn't mean your project is now on GitHub.

It only creates a **local Git repository**.

---

# `git init` vs GitHub

After:

```bash
git init
```

you have:

```text
Your Computer
     ↓
Local Git Repository
```

To connect it to GitHub, you need a remote:

```bash
git remote add origin <github-url>
```

Then you can push:

```bash
git push -u origin main
```

So:

```text
git init
   ↓
Local Git Repository
   ↓
git remote add origin
   ↓
GitHub Repository
```

---

# Complete First-Time Setup

Suppose you created a new project.

### Step 1 — Enter the project

```bash
cd my-project
```

### Step 2 — Initialize Git

```bash
git init
```

### Step 3 — Check status

```bash
git status
```

### Step 4 — Stage files

```bash
git add .
```

### Step 5 — Create first commit

```bash
git commit -m "Initial commit"
```

### Step 6 — Connect GitHub

```bash
git remote add origin <github-repository-url>
```

### Step 7 — Use `main`

```bash
git branch -M main
```

### Step 8 — Push

```bash
git push -u origin main
```

---

# What is `.git`?

`.git` is the directory where Git stores the repository's internal data.

It helps Git manage:

- Commits
    
- Branches
    
- References
    
- Repository configuration
    
- Git objects
    
- History
    

You normally don't need to edit anything inside `.git` manually.

---

# How to Check if Git is Initialized

Run:

```bash
git status
```

If the folder is a Git repository, Git will show information about the repository.

If it isn't, Git will tell you that the current directory is not a Git repository.

---

# `git init` in Simple Language

Imagine you have a normal folder:

```text
📁 MyProject
```

You tell Git:

```bash
git init
```

Git basically says:

> "Okay, I'll start managing the version history of this folder."

Then:

```text
📁 MyProject
   └── 📁 .git
```

Now Git is watching the project for version-control purposes.

---

# Important Difference

### `git init`

```text
Create a LOCAL Git repository
```

### `git remote add origin`

```text
Connect LOCAL repository to a REMOTE repository
```

### `git push`

```text
Send LOCAL commits to REMOTE
```

---

# Aadi Bhai Memory Trick 😎

Remember:

```text
git init
   ↓
Start Git
   ↓
Create .git
   ↓
Local repository ready
```

### One-line answer

> **`git init` initializes a Git repository in the current directory by creating the `.git` directory and enabling Git version control.**