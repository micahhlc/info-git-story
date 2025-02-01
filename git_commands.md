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


<!-- Setup project first time -->

# Clone repository
git clone <repo_url>

# Work on main branch

# Set the upstream branch (if not automatically set):
git branch --set-upstream-to=origin/main main

# Benefits of Setting an Upstream Branch
#	1.	Enable Simple git pull and git push
#	•	Without an upstream, git pull and git push require you to specify the remote branch:
# 	•	With an upstream set, you can simply do: 
git pull 
git push
# 	2.	Track Remote Changes Easily
git status

<!-- Start today's work -->

# Pull remote work on main or feature branch
# on main branch
git pull origin main
# on feature branch
git checkout feature-branch
git pull origin feature-branch
# when creating new feature
git checkout -b new-feature-branch 

# track changes
git status

# see what changed
git diff

# Once changes are ready, add specific files:
git add file1.js file2.css 
# add all files
git add .
# commit. use present tense
git commit -m "fix: login issue and update UI components"

# To push your branch to the remote repository:
git push origin feature-new-ui
# If the branch doesn’t exist on the remote yet, use:
git push --set-upstream origin feature-new-ui

<!-- Create a Pull Request (PR) -->
Go to GitHub/GitLab/Bitbucket and open a Pull Request (PR) to merge feature-new-ui into main. Wait for team feedback.

<!-- Sync Mid-Day with Team (Fetch & Merge) -->

# If team members have made updates while you were working:
git fetch origin
git merge origin/main
# OR, if working in a feature branch:
git checkout feature-new-ui
git merge origin/main

# If there are conflicts, resolve them manually, then:
git add .
git commit -m "resolve: xxx merge conflicts"

# Undo all uncommitted changes:
git checkout -- file.js

# Unstage a file
git reset file.js

# Undo the last commit and remove changes:
git reset --hard HEAD~1

# Finish Work – Merge and Push. Once your PR is approved and merged by the team:
# sync latest work from remote to local main branch
git checkout main 
git pull origin main 

# Delete the old branch (if no longer needed):
git branch -d feature-new-ui

# push branch deletion to remote
git push origin --delete feature-new-ui

<!-- End-of-Day Push and Sync -->
git status  # Check if any changes need to be committed
git add .
git commit -m "Commit: Completed feature X. end of day work."
git push origin main


<!-- Useful git commands -->
# Configure Git
git config --global user.name "Micah Cheng"
git config --global user.email "micahhlc@gmail.com"

# Clone a repository
git clone <repo_url>

# Check the current status of files
git status

# Fetch and merge latest changes from remote main branch
git pull origin main

# Create a new branch
git checkout -b feature-branch

# Switch to an existing branch
git checkout main

# Set upstream branch if needed
git branch --set-upstream-to=origin/main main

# Stage a specific file for commit
git add file.js

# Stage all changes for commit
git add .

# Commit changes with a message
git commit -m "Your commit message"

# Push a branch to remote repository
git push origin branch-name

# Push a new branch and set upstream tracking
git push --set-upstream origin feature-branch

# Fetch latest updates without merging
git fetch origin

# Merge a branch into the current branch
git merge branch-name

# Rebase a branch onto main
git rebase main

# Undo the last commit but keep changes
git reset --soft HEAD~1

# Undo the last commit and remove changes
git reset --hard HEAD~1

# Unstage a file (keep changes)
git reset file.js

# Undo changes in a specific file
git checkout -- file.js

# Delete a branch locally
git branch -d feature-branch

# Delete a branch forcefully (if unmerged)
git branch -D feature-branch

# Delete a remote branch
git push origin --delete feature-branch

# List all branches
git branch -a

# Show commit history
git log --oneline --graph --all

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

# Create an interactive rebase (rewrite commit history)
git rebase -i HEAD~3

# Abort a rebase in case of conflict
git rebase --abort

# Continue rebase after resolving conflicts
git rebase --continue

# Remove a file from all commits (rewrite history)
git filter-repo --path file.txt --invert-paths

# Force push rewritten history (use with caution)
git push origin main --force