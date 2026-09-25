# Git Basics

## What is Git?

Git is a **Version Control System (VCS)**.

It helps us track changes made to our code over time.

### Git can help us:

- Track code changes
    
- Save different versions of a project
    
- See what changed
    
- Go back to an older version
    
- Work with branches
    
- Collaborate with other developers
    

## Simple Definition

> **Git is like a time machine for your code.**

---

## Why Do We Need Git?

Imagine you are building a website.

You make changes every day:

```text
Website
   ↓
Version 1
   ↓
Version 2
   ↓
Version 3
   ↓
Version 4
```

Without Git, managing these versions manually can become difficult.

With Git, Git keeps track of your changes.

---

## Basic Git Flow

```text
Write / Modify Code
        ↓
Working Directory
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
     GitHub
```

---

## Important Git Terms

### Repository

A project managed by Git.

### Working Directory

The files you are currently working on.

### Staging Area

The place where you select changes for the next commit.

### Commit

A saved snapshot of your project.

### Branch

A separate development line.

### Remote

Another copy of the repository, usually stored online.

### GitHub

An online platform used to host Git repositories and collaborate.

---

## Git is Distributed

Git is a **Distributed Version Control System**.

This means every cloned repository contains its own Git history.

```text
              GitHub
                 ↑
                 ↓
        Remote Repository
                 ↑
                 ↓
        Local Repository
                 ↑
                 ↓
          Your Computer
```

---

## Most Basic Commands

### Check Git version

```bash
git --version
```

### Initialize Git

```bash
git init
```

### Check repository status

```bash
git status
```

### Add files

```bash
git add .
```

### Create a commit

```bash
git commit -m "Initial commit"
```

### View commit history

```bash
git log
```

### Push to GitHub

```bash
git push
```

### Get changes from GitHub

```bash
git pull
```

---

## The Most Important Concept

Remember this flow:

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
       ↓
   git push
       ↓
GitHub
```

### Aadi Bhai Memory Trick 😎

> **Git = tracks your code history.**

> **Commit = save a version.**

> **Branch = separate development line.**

> **Push = send your commits to GitHub.**

> **Pull = get changes from GitHub.**