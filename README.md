# Introduction to Git

Git is a distributed version control system that helps you track changes in your code, collaborate with others, and manage different versions of your projects. This guide covers the essential Git commands every developer should know.

## What is Git?

Git allows you to:
- Track changes in your files over time
- Collaborate with multiple developers on the same project
- Create branches to work on different features simultaneously
- Merge changes from different contributors
- Revert to previous versions when needed

## Basic Git Workflow

The typical Git workflow follows these steps:
1. **Initialize** or **clone** a repository
2. **Add** changes to the staging area
3. **Commit** changes with a descriptive message
4. **Push** changes to a remote repository (like GitHub)

## Essential Git Commands

### Repository Setup

#### `git init`
Creates a new Git repository in the current directory.
```bash
git init
```

#### `git clone`
Downloads a repository from a remote source (like GitHub) to your local machine.
```bash
git clone https://github.com/username/repository-name.git
```

### Basic Operations

#### `git status`
Shows the current state of your working directory and staging area.
```bash
git status
```

#### `git add`
Stages changes for commit. You can add specific files or all changes.
```bash
git add filename.txt          # Add specific file
git add .                     # Add all changes
git add *.js                  # Add all JavaScript files
```

#### `git commit`
Saves staged changes to the repository with a descriptive message.
```bash
git commit -m "Add user authentication feature"
git commit -am "Fix bug in login system"  # Add and commit in one step
```

#### `git push`
Uploads your local commits to a remote repository.
```bash
git push origin main          # Push to main branch
git push origin feature-name  # Push to specific branch
```

#### `git pull`
Downloads and merges changes from a remote repository to your local branch.
```bash
git pull origin main
```

### Viewing History and Changes

#### `git log`
Shows the commit history.
```bash
git log                       # Full commit history
git log --oneline            # Condensed view
git log --graph              # Visual branch representation
```

#### `git diff`
Shows differences between versions.
```bash
git diff                     # Changes in working directory
git diff --staged            # Changes in staging area
git diff HEAD~1              # Compare with previous commit
```

#### `git show`
Displays information about a specific commit.
```bash
git show commit-hash
git show HEAD                # Show latest commit
```

### Branching and Merging

#### `git branch`
Lists, creates, or deletes branches.
```bash
git branch                   # List all branches
git branch feature-login     # Create new branch
git branch -d feature-login  # Delete branch
```

#### `git checkout` / `git switch`
Switches between branches or commits.
```bash
git checkout main            # Switch to main branch
git checkout -b new-feature  # Create and switch to new branch
git switch main              # Modern alternative to checkout
git switch -c new-feature    # Create and switch (modern syntax)
```

#### `git merge`
Combines changes from one branch into another.
```bash
git checkout main
git merge feature-branch
```

### Remote Repository Management

#### `git remote`
Manages remote repository connections.
```bash
git remote -v                # View remote repositories
git remote add origin https://github.com/username/repo.git
git remote remove origin     # Remove remote connection
```

#### `git fetch`
Downloads changes from remote repository without merging.
```bash
git fetch origin
git fetch --all              # Fetch from all remotes
```

### Undoing Changes

#### `git reset`
Unstages changes or moves the branch pointer.
```bash
git reset filename.txt       # Unstage specific file
git reset --soft HEAD~1      # Undo last commit, keep changes staged
git reset --hard HEAD~1      # Undo last commit, discard changes
```

#### `git revert`
Creates a new commit that undoes previous changes.
```bash
git revert commit-hash       # Safely undo specific commit
```

#### `git checkout` (for files)
Discards changes in working directory.
```bash
git checkout -- filename.txt  # Discard changes to specific file
git checkout .                 # Discard all changes
```

### Stashing Changes

#### `git stash`
Temporarily saves changes without committing.
```bash
git stash                    # Stash current changes
git stash pop                # Apply and remove latest stash
git stash list               # View all stashes
git stash apply stash@{0}    # Apply specific stash
```

## Common Git Workflows

### Feature Branch Workflow
1. Create a new branch for your feature
2. Make changes and commit them
3. Push the branch to remote
4. Create a pull request
5. Merge after review

```bash
git checkout -b feature/user-profile
# Make your changes
git add .
git commit -m "Add user profile page"
git push origin feature/user-profile
```

### Collaborative Workflow
1. Pull latest changes from main
2. Create feature branch
3. Work on your changes
4. Push and create pull request
5. Merge after review

```bash
git pull origin main
git checkout -b feature/new-component
# Work on your feature
git add .
git commit -m "Implement new component"
git push origin feature/new-component
```

## Best Practices

### Commit Messages
- Use present tense ("Add feature" not "Added feature")
- Keep the first line under 50 characters
- Use imperative mood ("Fix bug" not "Fixes bug")
- Be descriptive but concise

### Examples of Good Commit Messages
```
Add user authentication system
Fix memory leak in image processing
Update README with installation instructions
Remove deprecated API endpoints
```

### General Tips
- Commit frequently with small, logical changes
- Always pull before starting new work
- Use branches for features and bug fixes
- Test your code before committing
- Write meaningful commit messages
- Use `.gitignore` to exclude unnecessary files

## Helpful Resources

- [Official Git Documentation](https://git-scm.com/doc)
- [GitHub's Git Handbook](https://guides.github.com/introduction/git-handbook/)
- [Interactive Git Tutorial](https://learngitbranching.js.org/)
- [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)

## Getting Help

```bash
git help <command>           # Get help for specific command
git <command> --help         # Alternative help syntax
git help                     # General help
```

## Squash
Simply, combines all the relevant selected commits into a single commit

---

Remember, Git might seem overwhelming at first, but mastering these basic commands will make you much more productive as a developer. Start with the basics and gradually incorporate more advanced features as you become comfortable!
