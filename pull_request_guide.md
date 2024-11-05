## in git user f1cheng who starts to have pull request
### fork in github web from upempty.

### as below git operations

### in f1cheng git web "Compare & pull request"  click to "Add a titile" and "Add a description".  


```
[root@iZbp1evissossq564e432eZ ~]# cd /myhome/programming/pr
[root@iZbp1evissossq564e432eZ pr]# git clone git@github.com:f1cheng/git.git--------------------------
Cloning into 'git'...
remote: Enumerating objects: 114, done.
remote: Total 114 (delta 0), reused 0 (delta 0), pack-reused 114 (from 1)
Receiving objects: 100% (114/114), 14.28 KiB | 7.14 MiB/s, done.
Resolving deltas: 100% (38/38), done.
[root@iZbp1evissossq564e432eZ pr]# cd git
[root@iZbp1evissossq564e432eZ git]# ls
README.md
[root@iZbp1evissossq564e432eZ git]# git remote -v
origin  git@github.com:f1cheng/git.git (fetch)
origin  git@github.com:f1cheng/git.git (push)
[root@iZbp1evissossq564e432eZ git]# git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/master
[root@iZbp1evissossq564e432eZ git]# git remote add upstream git@github.com:upempty/git.git------------
[root@iZbp1evissossq564e432eZ git]# git remote -v
origin  git@github.com:f1cheng/git.git (fetch)
origin  git@github.com:f1cheng/git.git (push)
upstream        git@github.com:upempty/git.git (fetch)
upstream        git@github.com:upempty/git.git (push)
[root@iZbp1evissossq564e432eZ git]# git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/master

[root@iZbp1evissossq564e432eZ git]# git checkout -b mydev origin/master-------------------------------
branch 'mydev' set up to track 'origin/master'.
Switched to a new branch 'mydev'
[root@iZbp1evissossq564e432eZ git]# git branch -a
  master
* mydev
  remotes/origin/HEAD -> origin/master
  remotes/origin/master
[root@iZbp1evissossq564e432eZ git]# ls
README.md
[root@iZbp1evissossq564e432eZ git]# vi README.md
[root@iZbp1evissossq564e432eZ git]# vi README.md
[root@iZbp1evissossq564e432eZ git]# git status
On branch mydev
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
[root@iZbp1evissossq564e432eZ git]# git add README.md---------------------------------------------------
[root@iZbp1evissossq564e432eZ git]# git status
On branch mydev
Your branch is up to date with 'origin/master'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md

[root@iZbp1evissossq564e432eZ git]# git commit -m 'recheck git operation'-------------------------------
[mydev cf82e71] recheck git operation
 1 file changed, 1 insertion(+)
[root@iZbp1evissossq564e432eZ git]# git status
On branch mydev
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
[root@iZbp1evissossq564e432eZ git]# git branch -a
  master
* mydev
  remotes/origin/HEAD -> origin/master
  remotes/origin/master
[root@iZbp1evissossq564e432eZ git]# git pull --rebase upstream master------------------------------------
From github.com:upempty/git
 * branch            master     -> FETCH_HEAD
 * [new branch]      master     -> upstream/master
Current branch mydev is up to date.
[root@iZbp1evissossq564e432eZ git]# git diff
[root@iZbp1evissossq564e432eZ git]# vi README.md
[root@iZbp1evissossq564e432eZ git]# git push origin mydev------------------------------------------------
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 2 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 286 bytes | 286.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'mydev' on GitHub by visiting:
remote:      https://github.com/f1cheng/git/pull/new/mydev
remote:
To github.com:f1cheng/git.git
 * [new branch]      mydev -> mydev
[root@iZbp1evissossq564e432eZ git]# git branch -a
  master
* mydev
  remotes/origin/HEAD -> origin/master
  remotes/origin/master
  remotes/origin/mydev
  remotes/upstream/master
  ```
  
## in upempty who accepts the pull request from f1cheng.
### way1: in web, to "Merge pull request"
### way2: cli as below git operations

```
  git clone git@github.com:upempty/git.git
  git checkout -b f1cheng-mydev master
  git pull git@github.com:f1cheng/git.git mydev
  git checkout master
  git merge --no-ff f1cheng-mydev #to add the commit comments.
  git push origin master
```


## precondition here is example for upempty git user.
``` 
[root@VM-16-14-centos git]# ssh-keygen -t ed25519 -C "184918308@qq.com"
Generating public/private ed25519 key pair.
Enter file in which to save the key (/root/.ssh/id_ed25519):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /root/.ssh/id_ed25519
Your public key has been saved in /root/.ssh/id_ed25519.pub
The key fingerprint is:
SHA256:hnqy4JENxZpjacG5UoYKNZWUnRRp9JX9byBuslA7W0o 184918308@qq.com
The key's randomart image is:
+--[ED25519 256]--+
|  ooo*++  .o     |
| + +o =. .. .    |
|o * o.  .    .   |
|oo B   .  . . o  |
|o X   . S. o . o |
| + = . .. E +   o|
|  + + .  o O   . |
| . o +    +      |
|  . .            |
+----[SHA256]-----+
[root@VM-16-14-centos git]#
[root@VM-16-14-centos git]# cat ~/.ssh/id_ed25519.pub
``` 
### Copy to paste to empty's git repo "settings"->"SSH and GPG keys"->"New SSH key"

### then have the git repo rights for ssh git clone and git push.
