# git  
## git rebase a&letb1 overwrite here &a   
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
