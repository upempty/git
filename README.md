
Test for git revert  
222
## git rebase master  
git checkout master  
git pull  
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
### second 112333changes for review  
```  
git checkout b1  
git pull origin b1  
=======
```  
vi README.md  
git add .  
git commit -m $'a&b&a1'  
vi README.md  
git add .  
git commit --amend -m $'a&b&a'  
git log --oneline --all --decorate  
```  
git rebase origin/master  
```  
To resolve conflict issue  
vi README.md  
```  
git add .  
git rebase --continue  
----git checkout master  
----git merge b1  
git push origin master(git push origin HEAD:master)  

## amend not allow directly push to remote, but by force !!!:)  
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
