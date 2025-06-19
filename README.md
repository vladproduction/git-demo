# Git Demo

A comprehensive guide to Git version control commands and workflows.

## 📚 Useful Resources

- **Training Presentation**: DevTestOps-Version_Control_with_Git.pdf
- **Git Official Website**: https://git-scm.com/
- **ProGit Book (Russian)**: https://git-scm.com/book/ru/v2

## ⚙️ Initial Setup

| Command | Description |
|---------|-------------|
| `git config --global user.name "Your Name"` | Set your global username |
| `git config --global user.email "email@example.com"` | Set your global email |
| `git config --list` | View all configuration settings |
| `git config --global init.defaultBranch main` | Set default branch name to 'main' |

## 🚀 Repository Management

| Command | Description |
|---------|-------------|
| `git clone [repo-url]` | Clone a remote repository to local machine |
| `git init` | Initialize a new Git repository |
| `git remote -v` | View remote repositories and their URLs |
| `git remote add origin [url]` | Add a remote repository |
| `git remote remove origin` | Remove a remote repository |

## 📊 Status and Information

| Command | Description |
|---------|-------------|
| `git status` | Show working directory and staging area status |
| `git log` | Display commit history |
| `git log --oneline` | Show compact commit history |
| `git log --graph --oneline --all` | Visual branch and merge history |
| `git diff` | Show changes between working directory and staging |
| `git diff --staged` | Show changes between staging and last commit |
| `git show [commit-hash]` | Show details of a specific commit |

## 📝 Making Changes

| Command | Description |
|---------|-------------|
| `git add [filename]` | Stage specific file for commit |
| `git add .` | Stage all changes in current directory |
| `git add -A` | Stage all changes in entire repository |
| `git commit -m "message"` | Commit staged changes with message |
| `git commit -am "message"` | Stage and commit all tracked files |
| `git commit --amend` | Modify the last commit |

## 🔄 Synchronization

| Command | Description |
|---------|-------------|
| `git push` | Push commits to remote repository |
| `git push -u origin [branch]` | Push branch and set upstream tracking |
| `git push --force` | Force push (use with caution!) |
| `git pull` | Fetch and merge changes from remote |
| `git fetch origin` | Download changes without merging |
| `git fetch --all` | Fetch from all remotes |

## 🌿 Branch Management

| Command | Description |
|---------|-------------|
| `git branch` | List all local branches |
| `git branch -a` | List all branches (local and remote) |
| `git branch -d [branch]` | Delete a local branch |
| `git checkout -b [branch]` | Create and switch to new branch |
| `git checkout [branch]` | Switch to existing branch |
| `git switch [branch]` | Modern way to switch branches |
| `git switch -c [branch]` | Create and switch to new branch |
| `git merge [branch]` | Merge specified branch into current branch |
| `git merge --abort` | Abort a merge in progress |

## 🔀 Advanced Branch Operations

| Command | Description |
|---------|-------------|
| `git rebase origin/main` | Reapply commits on top of main branch |
| `git rebase -i HEAD~n` | Interactive rebase for last n commits |
| `git rebase --continue` | Continue rebase after resolving conflicts |
| `git rebase --abort` | Abort rebase operation |
| `git cherry-pick [commit-hash]` | Apply specific commit to current branch |

## ↩️ Undoing Changes

| Command | Description |
|---------|-------------|
| `git restore [filename]` | Restore file to last committed state |
| `git restore .` | Restore all files to last committed state |
| `git restore --staged [filename]` | Unstage a file |
| `git clean -xdf` | Remove all untracked files and directories |
| `git reset HEAD~1` | Undo last commit, keep changes in working directory |
| `git reset --soft HEAD~1` | Undo last commit, keep changes staged |
| `git reset --mixed HEAD^` | Undo last commit, unstage changes (default) |
| `git reset --hard HEAD^` | Undo last commit, discard all changes |
| `git revert [commit-hash]` | Create new commit that undoes specified commit |

## 📦 Stashing

| Command | Description |
|---------|-------------|
| `git stash` | Temporarily save uncommitted changes |
| `git stash push -m "message"` | Stash with descriptive message |
| `git stash list` | Show all stashes |
| `git stash pop` | Apply most recent stash and remove it |
| `git stash apply` | Apply most recent stash without removing it |
| `git stash drop` | Delete most recent stash |
| `git stash clear` | Delete all stashes |

### Stash Workflow Example:
```bash
git stash                    # Save current work
git checkout main           # Switch to main branch
# Fix urgent issue and commit
git checkout feature        # Return to feature branch
git stash pop              # Restore your work
```

## 🏷️ Tagging

| Command | Description |
|---------|-------------|
| `git tag` | List all tags |
| `git tag v1.0` | Create lightweight tag |
| `git tag -a v1.0 -m "Version 1.0"` | Create annotated tag with message |
| `git push origin v1.0` | Push specific tag to remote |
| `git push origin --tags` | Push all tags to remote |
| `git tag -d v1.0` | Delete local tag |

## 🖥️ GUI Tools

| Command | Description |
|---------|-------------|
| `git gui&` | Launch Git GUI in background |
| `gitk&` | Launch commit history viewer in background |

## 🔧 Remote Configuration

Configure different URLs for fetching and pushing:

```bash
git remote set-url origin https://example.com/fetch-repo.git      # Set fetch URL
git remote set-url --push origin https://example.com/push-repo.git # Set push URL
git remote -v                                                     # Verify configuration
```

Expected output:
```
origin  https://example.com/fetch-repo.git (fetch)
origin  https://example.com/push-repo.git  (push)
```

## 📝 Text Editor Commands (Vi/Vim)

When Git opens a text editor for commit messages:

| Command | Description |
|---------|-------------|
| `i` | Enter insert mode |
| `Esc` | Exit insert mode |
| `:wq` | Save and quit |
| `:q!` | Quit without saving |

## 🔀 Conflict Resolution

When merge conflicts occur:

1. **Identify conflicts**: `git status` shows files with conflicts
2. **Edit conflicted files**: Look for `<<<<<<<`, `=======`, `>>>>>>>` markers
3. **Choose or combine changes**: Remove markers and keep desired content
4. **Stage resolved files**: `git add [filename]`
5. **Complete merge**: `git commit` (or `git merge --continue` for rebase)
6. **Abort if needed**: `git merge --abort` or `git rebase --abort`

## 💡 Pro Tips

- Use `git log --oneline --graph` for a visual commit history
- Always pull before pushing to avoid conflicts
- Create descriptive commit messages
- Use branches for features and experiments
- Regularly backup important work with `git push`
- Use `git stash` when switching contexts quickly