# git-demo

//commit in master

**BASIC GIT COMMANDS**:
 - git config --global user.name
 - git config --global user.email
 - git clone [link for remote repo]
 - git remote -v
 - git status
 - git add [file name]
 - git add .
 - git commit -m "commit message"
 - git log
 - git push
 - git pull
 - git gui&
 - gitk&
 - git restore . 
 - git restore [file name]
 - git clean -xdf
 - git reset HEAD~1
 - git reset --soft HEAD~1
 - git reset --mixed HEAD^ (HEAD^ same as HEAD~1)
 - git reset --hard HEAD^
 - git revert [hash of commit wanted to revert into]
 -  "v" text editor --> insert btn --> type message --> :wq
 - (quit without saving anything) :q!
 - git checkout -b feature
 - git checkout main
 - git merge feature
 - git merge --abort
 - git diff
 - git fetch origin
 - git rebase origin/main
 - git rebase --abort
 - git rebase -i HEAD~n
 - git rebase --continue
