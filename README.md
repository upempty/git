## git 
```
==init version
git rev-list --reverse HEAD
git log --pretty=oneline --reverse | head -1
```
## git revert(undo commitid's changes, kept all others including before and after)  
git checkout master  
git fetch  
git reset --hard origin/master  
git pull  

git checkout -b user/f1cheng/rr(git branch -D user/f1cheng/rr for deletet branch)  
git revert commitid  
```  
if conflict: 
vi those conflict files to modify them  
git add file1  
git add file2  
git status  
git revert --continue  
```  
git push origin HEAD:refs/for/master(for review)  

## git rebase master  
git checkout master  
git pull  
### first modify  
```  
git checkout b1(git checkout -b user/f1cheng/wo)    
vi README.md  
git add .  
git commit -m $'final1'  
git log --oneline --all --decorate  
```  
### first review
```  
--if need rebase  
  git rebase origin/master  
  --To resolve conflict issue  
    vi README.md  
    git add .  
    git rebase --continue  
-------git checkout master(no)  
-------git merge b1(no)  
git push origin HEAD:master(git push origin HEAD:refs/for/master for review)  
  
--return to master  
  git checkout master  
  git pull origin master  

```  
### second changes for review  
```  
git checkout b1  
git pull origin b1  
vi README.md  
git add .  
git commit --amend -m $'final1-2'  
<git rebase ...
opt1:
git fetch
git rebase origin/master-----from remote
opt2:
git checkout master
git pull
git checkout b1
git rebase master------------from local repo
>
if based master changed: git rebase origin/master  
--To resolve conflict issue  
  vi README.md  
  git add .  
  git rebase --continue  
git push origin HEAD:master(git push origin HEAD:refs/for/master for review)  
  
--return to master  
git checkout master  
git pull origin master  
```  
### e.g:  
```  
Author: Cheng Fei <cheng.fei1026@gamil.com>---------review2
Date:   Sun Oct 1 20:33:57 2017 +0800

    1009--final1-2
----------------------------------------------------if master changed, then one more master orinal log here!
commit 62b2e83525189e8d0b24f042b4521777d835ba51-----review1
Author: Cheng Fei <cheng.fei1026@gamil.com>
Date:   Sun Oct 1 20:33:57 2017 +0800

    1009--final1

commit 14decb6d123b237970113523c3d0d9544cd75911----master original
Author: Cheng Fei <cheng.fei1026@gmail.com>
Date:   Mon Oct 9 22:37:52 2017 +0800

    Update README.md
```  

## amend not allow directly push to remote, but by force !!!:)  
### recheck
vi README.md  
git add .  
git commit --amend -m $'a&b&c'  
git push origin master  
```  
Username for 'https://github.com': yourname  
Password for 'https://yourname@github.com':  
To https://github.com/yourname/git.git  
 ! [rejected]        master -> master (non-fast-forward)  
error: 无法推送一些引用到 'https://github.com/yourname/git.git'  
提示：更新被拒绝，因为您当前分支的最新提交落后于其对应的远程分支。  
提示：再次推送前，先与远程变更合并（如 'git pull ...'）。详见  
提示：'git push --help' 中的 'Note about fast-forwards' 小节.  
```  
git push -f origin master  
rebase again and again, review  
  

