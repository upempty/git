# git   
## git rebase master&git merge branch  
git checkout master  
git pull  
git checkout b1  
```  
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

