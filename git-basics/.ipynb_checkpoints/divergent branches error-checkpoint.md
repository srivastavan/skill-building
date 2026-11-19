## Divergent branches error or message

When getting message such as -
```bash
(base) namrata@Namratas-MacBook-Pro-2 andrej-karpathy-Neural Networks-Zero to Hero % git push
To [https://github.com/srivastavan/skill-building.git](https://github.com/srivastavan/skill-building.git)
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to '[https://github.com/srivastavan/skill-building.git](https://github.com/srivastavan/skill-building.git)'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
(base) namrata@Namratas-MacBook-Pro-2 andrej-karpathy-Neural Networks-Zero to Hero % git pull 
remote: Enumerating objects: 7, done.
remote: Counting objects: 100% (7/7), done.
remote: Compressing objects: 100% (6/6), done.
remote: Total 6 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (6/6), 2.47 KiB | 281.00 KiB/s, done.
From [https://github.com/srivastavan/skill-building](https://github.com/srivastavan/skill-building)
   9469d84..6ea2c75  main       -> origin/main
hint: You have divergent branches and need to specify how to reconcile them.
hint: You can do so by running one of the following commands sometime before
hint: your next pull:
hint: 
hint:   git config pull.rebase false  # merge
hint:   git config pull.rebase true   # rebase
hint:   git config pull.ff only       # fast-forward only
hint: 
hint: You can replace "git config" with "git config --global" to set a default
hint: preference for all repositories. You can also pass --rebase, --no-rebase,
hint: or --ff-only on the command line to override the configured default per
hint: invocation.
fatal: Need to specify how to reconcile divergent branches.
```
#### **Run the following commands (GPT suggestion) -**

```bash
# Temporarily save the uncommitted change
git stash push -m "Save local changes before merging"

# Bring in GitHub's commits and merge with your local commit
git pull --no-rebase origin main

# Push the combined history
git push origin main

# Restore your uncommitted change
git stash pop
```

### Explaination of the logic -

1. Temporarily save the uncommitted change

```bash
git stash push -m "Save local changes before merging"
```

This stores my uncommitted changes in Git’s local stash and cleans the working directory.
- `push` creates a stash entry.
- `-m` gives it a descriptive message.
- In this case, it saves the modification to `../.DS_Store`.
- Existing commits stay on the branch.
**By default, this does not save new, untracked files. Use `git stash push -u` to save untracked files**

2. Download and merge GitHub’s commits

```bash
git pull --no-rebase origin main
```
- `origin` is the name of my GitHub remote.
- `main` is the remote branch to fetch.
- `--no-rebase` tells Git to combine the histories using a merge.

3. Push the combined history

```bash
git push origin main
```
This sends my local main branch’s commits (including the merge) to GitHub. Uncommitted and stashed changes are not uploaded.

4. Restore your uncommitted change

```bash
git stash pop
```
This reapplies the most recent stash to our working directory. If successful, Git removes that stash entry. Our .DS_Store modification becomes an uncommitted change again.
