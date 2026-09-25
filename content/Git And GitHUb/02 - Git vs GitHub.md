# Git vs GitHub

## What is Git?

**Git** is a Version Control System.

It is a software/tool that runs on your computer.

Git helps you:

- Track changes
    
- Create commits
    
- Create branches
    
- Merge branches
    
- View project history
    
- Restore previous versions
    
- Work offline
    

### Simple Meaning

> **Git manages your code history on your computer.**

---

## What is GitHub?

**GitHub** is an online platform for hosting Git repositories.

GitHub provides features such as:

- Remote repositories
    
- Pull Requests
    
- Issues
    
- Code collaboration
    
- Code reviews
    
- GitHub Actions
    
- Project management
    

### Simple Meaning

> **GitHub is an online place where you can store and collaborate on Git repositories.**

---

# Git vs GitHub

|Git|GitHub|
|---|---|
|Software/tool|Online platform|
|Works mainly on your computer|Works online|
|Tracks changes|Hosts Git repositories|
|Creates commits|Stores pushed commits|
|Creates branches|Hosts remote branches|
|Can work without internet|Requires internet for online features|
|Command-line tool|Web platform + Git hosting|

---

# Simple Example

Suppose you have a project:

```text
Aadi-Brain/
├── frontend/
├── backend/
└── README.md
```

You initialize Git:

```bash
git init
```

Now Git starts tracking the project locally.

```text
Your Computer
      ↓
     Git
      ↓
Local Repository
```

Then you create a repository on GitHub and connect it:

```text
Your Computer
      ↓
     Git
      ↓
Local Repository
      ↓
    GitHub
      ↓
Remote Repository
```

---

# Git Commands vs GitHub

Most Git operations are performed using Git commands:

```bash
git init
git add .
git commit -m "message"
git branch
git switch
git merge
git push
git pull
```

GitHub provides the online interface and collaboration features around the repository.

For example, after pushing a branch to GitHub, you can create a **Pull Request** on GitHub.

---

# Important Difference

### Git

```text
Git = Version Control
```

### GitHub

```text
GitHub = Git Repository Hosting + Collaboration
```

---

# Can Git Work Without GitHub?

**Yes.**

You can use Git completely locally.

Example:

```bash
git init
git add .
git commit -m "First commit"
```

You don't need GitHub for these commands.

---

# Can GitHub Work Without Git?

GitHub is built around Git repositories and Git workflows.

You can perform many actions through the GitHub website, but understanding Git is important for working effectively with repositories locally.

---

# Easy Real-Life Example

Think about a college project.

### Git

Like a notebook that keeps the history of your project:

```text
Day 1 → Version 1
Day 2 → Version 2
Day 3 → Version 3
```

### GitHub

Like an online place where you keep that project and allow others to access and collaborate on it.

---

# Aadi Bhai Memory Trick 😎

Remember:

```text
Git
 ↓
Version Control
 ↓
Tracks your project history
```

```text
GitHub
 ↓
Online Platform
 ↓
Hosts Git repositories
 ↓
Collaboration
```

### One-line answer

> **Git is the tool that manages version control, while GitHub is an online platform for hosting Git repositories and collaborating on them.**