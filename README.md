# git
git practise
1. git checkout -b b1
2. git add .
3. git commit -m 'Add init readme'
4. git push origin HEAD

"Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/f1cheng/git.git
  [new branch]      HEAD -> b1
git branch -a
  b1
  master
  remotes/origin/HEAD -> origin/master
  remotes/origin/b1
  remotes/origin/master
"
5. git checkout master
"README.md's content is changed to master's which is fetching from remote server
切换到分支 'master'
您的分支与上游分支 'origin/master' 一致。
"
6. make changes
7. git add .
8. git commit -m 'add 2'
9. git push origin HEAD
10. git checkout b1
11. git rebase origin/master
"there is conflict and merge flags in files. vi one by one, manually to change them".
12. git rebase --continue
13. git add .
14. 
