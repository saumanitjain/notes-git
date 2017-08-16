VC:-  http://techbus.safaribooksonline.com/video/software-engineering-and-development/version-control/ 
1:-Version control is a tool(utility) that allows us to manage the history of our changes.
2:- It allows us to merge the code when more then 1 team member is working on a project.
3:- Make us aware from the merge conflict.
working directory (all files)---- Staging Area  (tracking files)-------Repository (committed files)

Downlod git from : http://git-scm.com
$ git help <command name>
###initial setting###
$ git config --global user.name "Saurabh Jain"
$ git config --global user.email "saurabh.manit.jain@gmail.com"
$ git config --global core.editor "'C:/Program Files (x86)/Notepad++/notepad++.exe' -multiInst -nosession"
###check setting###  
git config --list
#Create git project
$git init
ReadMe.md (md - Mark down)
.gitignore : holds all the file/folder names which we dont want to checkin in VC
$git status # show all staging area files and untracked files
$git add <file name> /  git add . # to add all files in staging area
$git log # shows all commits
$git log --oneline # shows all commits in one line
$git diff   or git diff <file name> # git diff compare the local files from staging area file
$git diff HEAD <file name>  # compare the local files from repository
$git diff HEAD~1 <file name>  # compare the local files from repository
$git diff --staged # compare staged file/s from last commited file/s
$git diff <commit number> # ie git diff 6d6afa1 -  get it from git log --oneline
$git commit -m "message"
$git commit  # dont add -m 'message' to add multiline commit message (actually it open a configured text editor to add multiline comments)
##Undo the chages
$git checkout HEAD~1 <File Name> # very usefull when we want to revert some file/s or all files committed under some commit.
$git reset --hard # remove all changes and set the repository to head
$git reset <commit number> <file Name> # git reset 23faf41 ReadMe.md
#### create and add a .gitignore file and mention all the files which we dont want to commit into it.
$git add -f <file name> # forecely add even it is in .gitignore file.
#### Remote Repository
$git clone <url> #if u already have a project
$git push -u <not required default> <where> <what>
$git remote add origin <url> # add/change the origin if we want to push/create to code in some other repository
$git push origin master  #it may ask password of remote repository if u have not generated and add ssh key in remote repository
$git remote -v #returns remote repository url for get/fetch
###Use branch
$git branch -a #shows all branch
$git branch <branch name> # git branch feature1; create a new branch-feature1
$git checkout <branch name> # git chechout feature1 ; switch to newly created feature1 branch
# or
$git branch -b <branch name> # git branch -b feature1; create a new branch and switch to newly created branch
$git branch -d  <branch name> # git branch -d feature1 ; delete a branch;(-D: for force delete
$git log --oneline --all --decorate --graph
$git merge <branch name> # git merge feature1 ; merge the feature1 branch into current branch
############## Fork ###########
#a collaborator can fork (replicala of a branch in his own account) a branch and can update it and later on raise a merge/pull request to merge it in main user branch to merge it.
# if main user is updating main repo then user's repo will not be in sysc
#so keep user repo in sync follow below setps.
$ git remote add upstream <http/ssh url of main repo>
$ git remote -v
$ git pull upstream master 
$ git push origin master
############
$git rebase development/master. # adds all the changes from development/master branch into ur brach and then add ur changes on the top of those changes

