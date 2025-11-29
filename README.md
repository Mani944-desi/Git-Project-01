ubuntu@ip-172-31-21-255:~/Git-Project-01$ git checkout main
Already on 'main'
Your branch is up to date with 'origin/main'.
ubuntu@ip-172-31-21-255:~/Git-Project-01$ git merge feature-logging
Already up to date.

*******************************************************************************************************************************
ubuntu@ip-172-31-21-255:~/Git-Project-01$ git log --oneline --graph --all --decorate -10
* 1534ef5 (HEAD -> main, origin/main) Commit after new stash proof demo
* 8c077b9 Add stash test line
| * 6c37252 (refs/stash) On feature-improve-script2: new stash proof
|/| 
| * 33de9ad index on feature-improve-script2: 1a0af37 Improve script2 with extra logs
|/  
* 1a0af37 (feature-improve-script2) Improve script2 with extra logs
* 8afe9b6 Update script1 from main branch
* 9d7777f (feature-logging) Add logging message to script1 in feature-logging branch
* 459afe5 Initial commit with script1.sh and script2.sh
* 819d678 Initial commit

********************************************************************************************************************************

ubuntu@ip-172-31-21-255:~/Git-Project-01$ git stash list
stash@{0}: On feature-improve-script2: new stash proof

***********************************************************************************************************************************
ubuntu@ip-172-31-21-255:~/Git-Project-01$ git stash pop
Auto-merging script1.sh
CONFLICT (content): Merge conflict in script1.sh
On branch main
Your branch is up to date with 'origin/main'.

Unmerged paths:
  (use "git restore --staged <file>..." to unstage)
  (use "git add <file>..." to mark resolution)
        both modified:   script1.sh

no changes added to commit (use "git add" and/or "git commit -a")
The stash entry is kept in case you need it again.

*****************************************************************************************************************************************

ubuntu@ip-172-31-21-255:~/Git-Project-01$ git status 
On branch main
Your branch is up to date with 'origin/main'.

Unmerged paths:
  (use "git restore --staged <file>..." to unstage)
  (use "git add <file>..." to mark resolution)
        both modified:   script1.sh

no changes added to commit (use "git add" and/or "git commit -a")
ubuntu@ip-172-31-21-255:~/Git-Project-01$ git reflog | grep stash
1534ef5 HEAD@{1}: commit: Commit after new stash proof demo
8c077b9 HEAD@{6}: commit: Add stash test line

**************************************************************************************************************************************************

ubuntu@ip-172-31-21-255:~/Git-Project-01$ git stash list
stash@{0}: On feature-improve-script2: new stash proof
ubuntu@ip-172-31-21-255:~/Git-Project-01$ git branch -vv
  feature-improve-script2 1a0af37 Improve script2 with extra logs
  feature-logging         9d7777f Add logging message to script1 in feature-logging branch
* main                    1534ef5 [origin/main] Commit after new stash proof demo

***************************************************************************************************************************************************

ubuntu@ip-172-31-21-255:~/Git-Project-01$ git branch --merged
  feature-improve-script2
  feature-logging
* main

************************************************************************************************************************************************

ubuntu@ip-172-31-21-255:~/Git-Project-01$ git reflog | grep rebase
1a0af37 HEAD@{14}: rebase (finish): returning to refs/heads/feature-improve-script2
1a0af37 HEAD@{15}: rebase (pick): Improve script2 with extra logs
8afe9b6 HEAD@{16}: rebase (start): checkout main

**********************************************************************************************************************************************

ubuntu@ip-172-31-21-255:~/Git-Project-01$ git reflog | grep stash
1534ef5 HEAD@{1}: commit: Commit after new stash proof demo
8c077b9 HEAD@{6}: commit: Add stash test line

*************************************************************************************************************************************************

ubuntu@ip-172-31-21-255:~/Git-Project-01$ git log --oneline --graph --all --decorate -20
* 1534ef5 (HEAD -> main, origin/main) Commit after new stash proof demo
* 8c077b9 Add stash test line
| * 6c37252 (refs/stash) On feature-improve-script2: new stash proof
|/| 
| * 33de9ad index on feature-improve-script2: 1a0af37 Improve script2 with extra logs
|/  
* 1a0af37 (feature-improve-script2) Improve script2 with extra logs
* 8afe9b6 Update script1 from main branch
* 9d7777f (feature-logging) Add logging message to script1 in feature-logging branch
* 459afe5 Initial commit with script1.sh and script2.sh
* 819d678 Initial commit

*******************************************************************************************************************************************************
