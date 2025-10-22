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

# show git merge in graph

git log --oneline --graph --decorate --all

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
