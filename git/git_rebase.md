# Ensure you are on your feature branch
git checkout feature-branch

# Fetch the latest changes from remote without merging
git fetch origin

# Rebase your feature branch on top of the latest main branch
git rebase origin/main

# If there are conflicts, resolve them manually in the files

# After resolving conflicts, stage the fixed files
git add <conflicted-file>

# Continue rebase after fixing conflicts
git rebase --continue

# If too many conflicts and you want to cancel the rebase
git rebase --abort

# If rebase is successful and branch was already pushed before, force push is required
git push --force origin feature-branch

# If you want to check the list of commits before rebasing
git log --oneline --graph --all

# To check which branch is currently checked out
git branch

# To check which upstream branch your current branch is tracking
git branch -vv