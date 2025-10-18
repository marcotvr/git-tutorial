# GitHub Tutorial

Welcome to this comprehensive guide on how to use GitHub! This tutorial will walk you through the essential concepts and workflows you need to know.

## Table of Contents
1. [What is GitHub?](#what-is-github)
2. [Getting Started](#getting-started)
3. [Basic Git Commands](#basic-git-commands)
4. [Working with Repositories](#working-with-repositories)
5. [Branching and Merging](#branching-and-merging)
6. [Pull Requests](#pull-requests)
7. [Collaboration Workflow](#collaboration-workflow)
8. [Best Practices](#best-practices)

## What is GitHub?

GitHub is a web-based platform that uses Git for version control. It allows developers to:
- Store and manage code in repositories
- Track changes and collaborate with others
- Review code through pull requests
- Manage projects with issues and project boards
- Host documentation and websites

**Git vs GitHub:**
- **Git** is a version control system that tracks changes in your code
- **GitHub** is a hosting service for Git repositories with additional collaboration features

## Getting Started

### Prerequisites
1. **Install Git**: Download from [git-scm.com](https://git-scm.com/)
2. **Create a GitHub account**: Sign up at [github.com](https://github.com/)

### Configure Git
```bash
# Set your name and email
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# Verify your configuration
git config --list
```

### Authentication
GitHub recommends using SSH keys or Personal Access Tokens (PAT) for authentication.

**Generate SSH Key:**
```bash
ssh-keygen -t ed25519 -C "your.email@example.com"
# Add the key to your GitHub account under Settings > SSH and GPG keys
```

## Basic Git Commands

### Initialize a Repository
```bash
# Create a new local repository
git init

# Clone an existing repository
git clone https://github.com/username/repository.git
```

### Check Status and History
```bash
# See which files have changed
git status

# View commit history
git log

# View compact history
git log --oneline
```

### Making Changes
```bash
# Add specific file to staging area
git add filename.txt

# Add all changes
git add .

# Commit changes with a message
git commit -m "Your descriptive commit message"

# Add and commit in one step (for tracked files)
git commit -am "Your commit message"
```

### Viewing Changes
```bash
# See unstaged changes
git diff

# See staged changes
git diff --staged

# See changes in a specific commit
git show <commit-hash>
```

## Working with Repositories

### Creating a New Repository on GitHub
1. Click the "+" icon in the top right corner
2. Select "New repository"
3. Enter repository name and description
4. Choose public or private
5. Optionally add README, .gitignore, and license
6. Click "Create repository"

### Connecting Local Repository to GitHub
```bash
# Add remote repository
git remote add origin https://github.com/username/repository.git

# Verify remote
git remote -v

# Push to GitHub
git push -u origin main
```

### Syncing with Remote
```bash
# Download changes from remote
git fetch origin

# Download and merge changes
git pull origin main

# Push local commits to remote
git push origin main
```

## Branching and Merging

Branches allow you to work on different features independently.

### Branch Commands
```bash
# List all branches
git branch

# Create a new branch
git branch feature-name

# Switch to a branch
git checkout feature-name

# Create and switch to a new branch
git checkout -b feature-name

# Modern alternative (Git 2.23+)
git switch feature-name
git switch -c feature-name
```

### Merging Branches
```bash
# Switch to the branch you want to merge into
git checkout main

# Merge another branch into current branch
git merge feature-name

# Delete a branch after merging
git branch -d feature-name
```

### Handling Merge Conflicts
When Git can't automatically merge changes, you'll need to resolve conflicts manually:

1. Open the conflicted files
2. Look for conflict markers: `<<<<<<<`, `=======`, `>>>>>>>`
3. Edit the file to resolve conflicts
4. Remove conflict markers
5. Stage the resolved files: `git add <file>`
6. Complete the merge: `git commit`

## Pull Requests

Pull Requests (PRs) are GitHub's way of proposing changes and reviewing code.

### Creating a Pull Request
1. Push your branch to GitHub: `git push origin feature-name`
2. Go to your repository on GitHub
3. Click "Compare & pull request" button
4. Add a title and description
5. Select reviewers if needed
6. Click "Create pull request"

### Pull Request Best Practices
- Write clear, descriptive titles
- Explain what changes were made and why
- Reference related issues using `#issue-number`
- Keep PRs focused and reasonably sized
- Respond to reviewer comments promptly
- Update your branch if needed: `git push origin feature-name`

### Reviewing Pull Requests
1. Go to the "Pull requests" tab
2. Click on a PR to review
3. View the "Files changed" tab
4. Add comments on specific lines
5. Submit your review (Approve, Request changes, or Comment)

## Collaboration Workflow

### Typical GitHub Workflow
1. **Fork** the repository (for open source projects)
2. **Clone** your fork locally
3. **Create a branch** for your feature
4. **Make changes** and commit them
5. **Push** to your fork on GitHub
6. **Create a Pull Request** to the original repository
7. **Address review feedback** if needed
8. **Merge** when approved

### Keeping Your Fork Updated
```bash
# Add upstream remote (original repository)
git remote add upstream https://github.com/original-owner/repository.git

# Fetch upstream changes
git fetch upstream

# Merge upstream changes into your main branch
git checkout main
git merge upstream/main

# Push updates to your fork
git push origin main
```

## Best Practices

### Commit Messages
- Use present tense: "Add feature" not "Added feature"
- Be clear and descriptive
- Keep the first line under 50 characters
- Add detailed description after a blank line if needed

**Example:**
```
Add user authentication feature

- Implement login and logout functionality
- Add password hashing with bcrypt
- Create session management
```

### Repository Organization
- Use a clear README.md to explain your project
- Add a .gitignore file to exclude unnecessary files
- Include a LICENSE file
- Use descriptive branch names: `feature/user-auth`, `bugfix/login-error`

### Security
- Never commit sensitive data (passwords, API keys, tokens)
- Use environment variables for secrets
- Add sensitive files to .gitignore
- Review PRs carefully for security issues

### Issues and Project Management
- Use GitHub Issues to track bugs and features
- Label issues for better organization
- Link commits and PRs to issues using `#issue-number`
- Use GitHub Projects for project planning

### Code Review
- Review code thoroughly before approving
- Be constructive and respectful in feedback
- Test changes locally when possible
- Look for bugs, security issues, and code quality

## Additional Resources

- [GitHub Docs](https://docs.github.com/)
- [Git Documentation](https://git-scm.com/doc)
- [GitHub Learning Lab](https://lab.github.com/)
- [Pro Git Book](https://git-scm.com/book/en/v2)

## Common Commands Quick Reference

```bash
# Setup
git init                          # Initialize repository
git clone <url>                   # Clone repository

# Basic workflow
git status                        # Check status
git add <file>                    # Stage changes
git commit -m "message"           # Commit changes
git push origin <branch>          # Push to remote

# Branching
git branch                        # List branches
git checkout -b <branch>          # Create and switch to branch
git merge <branch>                # Merge branch

# Syncing
git pull origin <branch>          # Pull changes
git fetch origin                  # Fetch changes

# History
git log                           # View commits
git diff                          # View changes

# Undo
git checkout -- <file>            # Discard changes
git reset HEAD <file>             # Unstage file
git revert <commit>               # Revert commit
```

---

Happy coding and collaborating on GitHub! 🚀