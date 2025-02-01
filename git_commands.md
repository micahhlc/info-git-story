<!-- Set Global Git Configurations -->

# Set your name and email (used for commits):
git config --global user.name "Micah Cheng"
git config --global user.email "micahhlc@gmail.com"

# Enable colorized output (optional but helpful):
git config --global color.ui auto

# Set default branch name
git config --global init.defaultBranch main

# Check config
git config --list


<!-- Common commands -->

# Clone a repository
git clone <repo_url>

# Check the current status of files
git status

# see what changed
git diff

# Show commit history
git log --oneline --graph --all

# Fetch and merge latest changes from remote main branch
git pull origin main

# Fetch latest updates without merging
git fetch origin

# Merge a branch into the current branch
git merge branch-name


# Switch to an existing branch
git checkout main
# Create a new branch
git checkout -b feature-branch
# Undo changes in a specific file
git checkout -- file.js

# Set upstream branch if needed
git branch --set-upstream-to=origin/main main
# Delete a branch locally
git branch -d feature-branch
# Delete a branch forcefully (if unmerged)
git branch -D feature-branch
# List all branches
git branch -a

# Push a new branch and set upstream tracking
git push --set-upstream origin feature-branch
# Push a branch to remote repository
git push origin branch-name
# Delete a remote branch
git push origin --delete feature-branch
# Force push rewritten history (use with caution)
git push origin main --force


# Stage a specific file for commit
git add file.js
# Stage all changes for commit
git add .


# Commit changes with a message
git commit -m "Your commit message"


# Rebase a branch onto main
git rebase main
# Create an interactive rebase (rewrite commit history)
git rebase -i HEAD~3
# Abort a rebase in case of conflict
git rebase --abort
# Continue rebase after resolving conflicts
git rebase --continue


# Undo the last commit but keep changes
git reset --soft HEAD~1
# Undo the last commit and remove changes
git reset --hard HEAD~1
# Unstage a file (keep changes)
git reset file.js


# Stash current changes (save for later)
<!-- Git won’t let you git pull if you have local modifications.
Solution: Stash your changes, pull the latest updates, then apply the stashed changes. -->
git stash
# Apply the latest stash
git stash pop
# Discard the latest stash
git stash drop
# Show all stashes
git stash list


# Remove a file from all commits (rewrite history)
git filter-repo --path file.txt --invert-paths