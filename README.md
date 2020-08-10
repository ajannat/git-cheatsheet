# git-cheatsheet

Git is a Version Control System(VCS). One of the primary function of git is keeping track of every changes of our project. To release a new version of our project we do not need to copy and paste the previous version to a new folder/directory every time. We can easily go to any version of our project by using some basic git commands. We do not need to get our hands dirty to make any changes to our project rather we simply run the commands and git will do the rest.

Besides, there are branch system on git by which we can easily add a new feature to our project and then test it to see if we need the new feature or not. We can easily add or delete the feature using git commands and we don't need to go to every files and manually remove codes for the new feature.

Enough talking!!! Now let's get familiar with some useful git commands-

__Configuring git -__ \
If we want to configure git globally on our desktop, we simply need to run the following commands using command line.
```
git config --global user.name <Your Name>
git config --global user.email <yourEmail@email.com>
```
__Initializing git -__ \
To setup a git repository or initialize git inside a folder, we have to run the following command which will initialize an empty git repository inside that folder.
```
git init
```
__Clonning a git repository -__ \
We can clone any git repositoy using SSH key or HTTPS web url. To use SSH key we have to set it up first. We can clone with HTTPS by running the following command.
```
git clone <web-url>
ex: git clone https://github.com/ajannat/git-cheatsheet.git
```
__Check status -__\
After initializing git or clonning a git repo if we do any changes to any files we can check the current status of the repository by the following command.
```
git status
```
__Adding / Staging files -__\
Once we run the 'git status' command we can see the untracked(new /  modified / deleted) files. We can add the files to the staging area by running the following commands.
```
git add <filename> --stage one particular file
ex: git add README.md
git add . --stage all new and modified files
```
There are a few more add commands having different functionalities like -
```
git add -u stage modified and deleted files
git add -A -- stage all(new, modified, deleted) files
git add --all --stage all(new, modified, deleted) files
```
__Unstaging files -__\
We can also unstage the files from the staging area before committing by running the following commands.
```
git reset <filename> --unstage one particular file
ex: git reset README.md
git reset --unstage all files
```
__Committing on git -__\
Committing is the final decision that we want to keep the changes to our git repo. We need to add a commit message with each commit so that later on we can easily understand the reason behind that particular commit. To commit we have to run the following command.
```
git commit -m "our message"
```
__Deleting the last commit -__\
We can revert our last commit before pushing out code to the repo by using the following command.
```
git reset HEAD~
```
__Git branch -__\
We can push our code to the master branch or we can create a new branch, do the changes there and then push to the created branch. We can use the following commands for git branching.
```
git branch --see the current branch
git checkout -b <branchName> --create a new branch
ex: git checkout -b newBranch
git checkout <branchName> --checkout to a particular branch
ex: git checkout newBranch
git branch -D <branchName> --delete a particular branch
ex: git branch -D newBranch
```
__Push code to repository -__
After committing the code successfully we need to push the code to our git repository by the following command.
```
git push origin <branchName>
ex: git push origin newBranch
```
__Pull changes from current branch -__\
Before we push we sometimes we need to pull changes from our git repository. For example, if two persons are working on the same branch and one person pushed his changes to that branch then the other person needs to pull the changes before he pushes any new changes otherwise it creates conflict while pushing. Pulling can be done by the following command.
```
git pull origin <branchName>
ex: git pull origin newBranch
```
__Check commit log -__\
We can easily check out commit logs using the following commands.
```
git log
git log --oneline --see the log in better version
```
We will get id with each log and we can go back to a previous version using those ids. For example, if the id of a particular log is 12345 we can run the following command to go the that version.
```
git checkout 12345
```
__Git merge -__\
Suppose we created a new branch named newBranch. We did some changes to the newBeanch and pushed the changes. Now if we want to merge the newBranch with our master branch we have to run the following commands.
```
git checkout master
git merge newBranch
```
__See differences between two commit -__\
If we want to see the differences between two commit we can do that by using the commit ids and running the following command.
```
git diff id1 id2
```