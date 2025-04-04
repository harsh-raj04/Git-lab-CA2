# Git Concepts Quick Reference

## HEAD in Git
- **HEAD**: Pointer to the current checkout in your repo (usually latest commit of current branch)
- **Reset Types**:
  - `--soft`: Moves HEAD but preserves staging/working areas
  - `--mixed`: Moves HEAD, resets staging area
  - `--hard`: Moves HEAD, resets staging area and working directory

## Merge Conflicts
- Occur when Git can't automatically reconcile differences between branches
- **Resolution Steps**:
  1. Identify conflicts with `git status`
  2. Edit files (look for `<<<<<<<`, `=======`, `>>>>>>>` markers)
  3. Add resolved files with `git add`
  4. Complete merge with `git commit`

## Merging vs. Rebasing

### Merging
- **Pros**: Preserves history, non-destructive
- **Cons**: Creates merge commits, can clutter history

### Rebasing
- **Pros**: Creates linear history, cleaner log
- **Cons**: Rewrites history (avoid on public branches), may require resolving conflicts multiple times

## Revert vs. Reset
- **Revert**: Creates new commit that undoes changes, preserves history
- **Reset**: Moves HEAD backward, changes history

## HEAD Movement Summary
- **Reset**: HEAD moves backward to target commit
- **Revert**: HEAD moves forward with new "undo" commit
- **Checkout**: Can create detached HEAD when pointing to commit instead of branch

## Conflict Resolution Approach
1. Understand both changes before resolving
2. Use tools like `git mergetool` when helpful
3. Test after resolving
4. Communicate with team on significant conflicts

## When to Use Each Strategy
- **Merge**: For shared branches, preserving history, integrating complete features
- **Rebase**: For local branches, cleaning up work before sharing, maintaining linear history
