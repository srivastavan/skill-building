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
(base) namrata@Namratas-MacBook-Pro-2 andrej-karpathy-Neural Networks-Zero to Hero % git status
On branch main
Your branch and 'origin/main' have diverged,
and have 1 and 2 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)
Changes not staged for commit:
  (use "git add \<file>..." to update what will be committed)
  (use "git restore \<file>..." to discard changes in working directory)
&#x9;modified:   ../.DS_Store
no changes added to commit (use "git add" and/or "git commit -a")
```