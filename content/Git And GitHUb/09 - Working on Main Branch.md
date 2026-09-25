# Working on Main Branch

## Can I Work Directly on `main`?

**Yes.**

Git does not require you to create a separate branch before making changes.

You can directly work on:

```text
main
```

Example:

```bash
git switch main
```

Then modify your code and commit:

```bash
git add .
git commit -m "Add login page"
git push
```

---

# What Happens When You Work on `main`?

Suppose your repository is:

```text
main
 |
 A
 |
 B
```

You modify your project and commit:

```text
main
 |
 A
 |
 B
 |
 C
```

The new commit `C` is directly added to `main`.

---

# Simple Workflow on Main

```text
Open Project
     ↓
Work on Code
     ↓
git status
     ↓
git add .
     ↓
git commit
     ↓
git push
```

Example:

```bash
git status

git add .

git commit -m "Add login functionality"

git push
```

---

# Is Working on Main Wrong?

**No.**

For a personal project, learning project, or small project, working directly on `main` can be completely fine.

For example:

```text
Personal Project
      ↓
    main
      ↓
   Work
      ↓
  Commit
      ↓
   Push
```

You don't have to create a feature branch every time.

---

# Why Do Developers Use Feature Branches?

Feature branches are useful when the project becomes more collaborative or complex.

Example:

```text
main
 |
 ├── feature-login
 ├── feature-payment
 └── bug-fix
```

Each branch can contain separate work.

This helps avoid putting unfinished changes directly into the main development line.

---

# Main vs Feature Branch

## Working Directly on Main

```text
main
 |
 A
 |
 B
 |
 C
```

You make all changes directly on `main`.

### Simple workflow

```bash
git add .
git commit -m "Add feature"
git push
```

---

## Working With a Feature Branch

```text
main
 |
 A
 |
 B
  \
   C
   ↑
feature-login
```

You work on `feature-login`.

```bash
git switch -c feature-login

git add .
git commit -m "Add login"

git push -u origin feature-login
```

Later, the branch can be merged into `main`.

---

# When Direct Main Is Useful

Working directly on `main` can make sense for:

- Personal projects
    
- Small projects
    
- Learning Git
    
- Quick experiments
    
- Projects where you are the only developer
    

Example:

```text
My Personal Project
        ↓
      main
        ↓
      Work
        ↓
     Commit
        ↓
      Push
```

---

# When Feature Branches Become Useful

Feature branches are especially useful when:

- Multiple developers are working together
    
- Features are large
    
- Changes need review
    
- Pull Requests are used
    
- You don't want unfinished work directly on the main branch
    
- Different features need to be developed simultaneously
    

Example:

```text
             feature-login
            /
main ──────●
            \
             feature-payment
```

---

# Important: `main` Is Not Automatically "Protected"

Git itself doesn't automatically prevent you from changing `main`.

Whether direct pushes to `main` are allowed can depend on repository settings and team practices.

A repository can have branch protection rules that require things such as Pull Requests or status checks before changes are merged.

---

# Aadi Bhai Example 😎

Suppose you're working alone on:

```text
Aadi-Brain
```

You add a new feature.

You can simply do:

```bash
git add .
git commit -m "Add chatbot feature"
git push
```

Done. ✅

No feature branch is required.

Later, if you start working with your friends:

```text
Aadi-Brain
      |
      ├── main
      ├── feature-chatbot
      ├── feature-auth
      └── bug-fix
```

Then branches become much more useful.

---

# Important Difference

### Working on Main

```text
Code
 ↓
main
 ↓
commit
 ↓
push
```

### Feature Branch Workflow

```text
main
 ↓
create feature branch
 ↓
work
 ↓
commit
 ↓
push branch
 ↓
Pull Request
 ↓
merge into main
```

---

# A Good Learning Approach

While learning Git, you can first practice directly on `main`.

Learn:

```text
main
 ↓
edit
 ↓
git add
 ↓
git commit
 ↓
git push
```

Then practice the branch workflow:

```text
main
 ↓
git switch -c feature
 ↓
edit
 ↓
git add
 ↓
git commit
 ↓
git push
 ↓
merge
```

This lets you understand both workflows.

---

# Aadi Bhai Memory Trick

> **You CAN work on `main`.**

> **A feature branch is a workflow choice, not a requirement of Git.**

```text
Personal project
      ↓
main is okay

Team project
      ↓
feature branches are often useful
```

### One-Line Definition

> **Working directly on `main` means making, committing, and pushing changes to the main branch without creating a separate feature branch.**