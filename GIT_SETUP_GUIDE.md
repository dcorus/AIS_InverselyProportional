# Git Repository Setup Guide

This guide explains how to create a new Git repository from a local folder and push it to GitHub.

## Prerequisites

- Git installed on your system
- A GitHub account
- (Optional) GitHub CLI (`gh`) for easier repository creation

## Method 1: Using Git and GitHub Web Interface

### Step 1: Initialize Local Repository

Navigate to your project folder and initialize Git:

```bash
cd /path/to/your/project
git init
```

### Step 2: Add Files to Git

Add all files you want to track:

```bash
git add .
```

Or add specific files:

```bash
git add file1.txt file2.txt
```

### Step 3: Create First Commit

```bash
git commit -m "Initial commit"
```

### Step 4: Create Repository on GitHub

1. Go to https://github.com
2. Click the "+" icon in the top right
3. Select "New repository"
4. Enter repository name and description
5. **Do NOT** initialize with README, .gitignore, or license (since you already have local content)
6. Click "Create repository"

### Step 5: Connect Local to Remote

GitHub will show you commands. Copy and run them:

```bash
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
git branch -M main
git push -u origin main
```

## Method 2: Using GitHub CLI (Recommended)

The GitHub CLI (`gh`) makes this process much simpler.

### Step 1: Install GitHub CLI

- **macOS**: `brew install gh`
- **Linux**: See https://github.com/cli/cli/blob/trunk/docs/install_linux.md
- **Windows**: Download from https://cli.github.com/

### Step 2: Authenticate

```bash
gh auth login
```

Follow the prompts to authenticate with your GitHub account.

### Step 3: Initialize and Create Repository

Navigate to your project folder:

```bash
cd /path/to/your/project
git init
git add .
git commit -m "Initial commit"
```

### Step 4: Create GitHub Repository

Create the repository on GitHub and push in one command:

```bash
gh repo create YOUR_REPO_NAME --public --source=. --push
```

Or for a private repository:

```bash
gh repo create YOUR_REPO_NAME --private --source=. --push
```

The `--source=.` flag tells GitHub CLI to use the current directory.

## Best Practices

### 1. Create a .gitignore File

Before adding files, create a `.gitignore` to exclude unwanted files:

```bash
# Example .gitignore for LaTeX projects
*.aux
*.log
*.out
*.toc
# Note: Be careful with *.pdf - you may want to keep some PDFs like figures
*.synctex.gz

# Example for Python projects
__pycache__/
*.pyc
.env
venv/

# Example for Node.js projects
node_modules/
.env
dist/
```

### 2. Write a Good README

Always include a `README.md` file explaining:
- What the project is
- How to use/build it
- Prerequisites and dependencies
- License information

### 3. Choose the Right Branch Name

Modern Git uses `main` as the default branch:

```bash
git branch -M main
```

### 4. Make Meaningful Commits

Use descriptive commit messages:

```bash
git commit -m "Add user authentication feature"
```

Not:

```bash
git commit -m "Update files"
```

## Troubleshooting

### Error: "remote origin already exists"

If you get this error, remove the existing remote and add it again:

```bash
git remote remove origin
git remote add origin https://github.com/USERNAME/REPO.git
```

### Error: "refusing to merge unrelated histories"

If GitHub was initialized with a README and you need to merge:

```bash
git pull origin main --allow-unrelated-histories
```

### Accidentally Committed Large Files

Remove from history:

```bash
git rm --cached large_file.zip
git commit -m "Remove large file"
```

For files already pushed, you may need `git filter-branch` or BFG Repo-Cleaner.

## Useful Git Commands

```bash
# Check repository status
git status

# View commit history
git log --oneline

# See what changed
git diff

# Undo changes to a file
git checkout -- filename

# Create a new branch
git checkout -b new-branch-name

# Push to remote
git push origin branch-name

# Pull latest changes
git pull origin main
```

## Additional Resources

- [Git Documentation](https://git-scm.com/doc)
- [GitHub Guides](https://guides.github.com/)
- [GitHub CLI Documentation](https://cli.github.com/manual/)
- [Atlassian Git Tutorial](https://www.atlassian.com/git/tutorials)

## Example: This Repository

This repository was created following these best practices:
- `.gitignore` excludes LaTeX auxiliary files
- `README.md` provides comprehensive documentation
- Organized structure with clear file naming
- Meaningful commit messages
