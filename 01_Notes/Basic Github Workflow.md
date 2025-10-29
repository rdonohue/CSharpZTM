# Daily workflow pattern:

#### Check what's changed
```
git status
```
#### Stage files for commit
```
git add .
```
#### Verify what's staged
```
git status
```
#### Commit your changes with a clear message
```
git commit -m "update notes for *topic*"
```
#### Sync with remote to avoid conflicts
```
git pull --rebase origin main
```
#### Push your work to Github
```
git push origin main
```
### Notes
- git diff --> inspect what changed before committing.
- git reset HEAD *file* --> unstage a file.
- ALways pull **before pushing** to keep your branch current.

## Working with Branches

```
git checkout -b feature/clean-architecture-summary   # create new branch
git add .
git commit -m "summarize Clean Architecture Ch. 1-2"
git checkout main
git pull --rebase origin main
git merge feature/clean-architecture-summary
git push origin main
git branch -d feature/clean-architecture-summary
```

## Recovery & Cleanup

```
git reset --soft HEAD~1    # undo last commit, keep changes staged
git reset --hard HEAD~1    # undo and discard last commit
git rebase -i HEAD~3       # combine or reorder last 3 commits
git log --oneline          # show condensed commit history
```

## Good Tips
- Keep commits small and descriptive -- it makes conflict resolution easier.
- Pull often, push often. Long gaps make merges harder. (What is the typical cadence? End of day?)
- Always test your code after resolving a conflict before pushing upstream.