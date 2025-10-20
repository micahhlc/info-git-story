# Ensure you are on the latest main branch

git checkout main
git pull origin main

# List all branches local and reote

git branch -a

# Create a new branch from main

git checkout -b feature-branch

# Work on the branch (modify files, make changes)

# View status of changes

git status

# Add all changes to staging

git add .

# Add a specific file to staging

git add <file-name>

# Commit changes with a message

git commit -m "Your commit message"

# Amend the last commit (only if not pushed yet)

git commit --amend -m "Updated commit message"

# Push the branch to remote for the first time and set upstream

git push --set-upstream origin feature-branch

# Continue working and pushing updates

git push origin feature-branch

# Fetch latest changes from remote

git fetch origin

# If main is updated and you need the latest changes in your branch

git checkout main
git pull origin main
git checkout feature-branch
git rebase origin/main

# Resolve conflicts if needed, then continue rebase

git add <resolved-file>
git rebase --continue

# If rebase gets messy, abort and return to previous state

git rebase --abort

# Merge feature branch into main (if not using PR)

git checkout main
git merge feature-branch

# If using PR, go to GitHub/GitLab, create a pull request, and wait for approval

# Once merged, delete the branch locally

git branch -d feature-branch

# Delete the branch remotely

git push origin --delete feature-branch

# List all local branches

git branch

# List all remote branches

git branch -r

# Show which remote branch your local branch is tracking

git branch -vv
