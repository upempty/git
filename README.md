# git  
## git practise a&b&a   
1. git checkout -b b1  
2. git add .  
3. git commit -m 'Add init readme'  
4. git push origin HEAD(git push origin HEAD:b1)  
5. git checkout master   
``` make changes ```  
7. git add .  
8. git commit -m 'add 2'  
9. git push origin HEAD(git push origin HEAD:master)  
10. git checkout b1  
11. git rebase origin/master  
```  there is conflict and merge flags in files.  
     vi one by one, manually to change them  
```  
12. git rebase --continue  
13. git rebase --skip  (optional)  
14. git push origin HEAD:b1  
15. git branch -a  
16. git checkout master  
17. git cherry-pick 1d249d02c3c892f886d0f79c4323a9088e65e10a  
18. git fetch origin  
19. git merge origin/master  
20. git push origin HEAD:master  
## common  
git add .  
git commit --amend  
git push origin HEAD:master( or git push?)  
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
git rebase master  
```  
To resolve conflict issue  
vi README.md  
```  
git add .  
git rebase --continue  
git checkout master  
git merge b1  
git push origin master(git push origin HEAD:master)  

##amend not allow directly push to remote, but by force!!!:)
vi README.md   
git add .  
git commit --amend -m $'a&b&c'  
git push origin master  
```    
Username for 'https://github.com': f1cheng  
Password for 'https://f1cheng@github.com':  
To https://github.com/f1cheng/git.git  
 ! [rejected]        master -> master (non-fast-forward)  
error: 无法推送一些引用到 'https://github.com/f1cheng/git.git'  
提示：更新被拒绝，因为您当前分支的最新提交落后于其对应的远程分支。  
提示：再次推送前，先与远程变更合并（如 'git pull ...'）。详见  
提示：'git push --help' 中的 'Note about fast-forwards' 小节。  
```   
git push -f origin master  

