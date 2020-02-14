#How to use Git

# Prerequisites for Remote Access from the Command Line
ssh-keygen -t rsa -C "<your_email_address>"
pbcopy < ~/.ssh/id_rsa.pub # filename may vary, use the filename given from the sshkeygen generation

# Go to Github
# Create/Login to Account
# ProfilePic > Settings > SSH and GPG Keys
# New SSH key
# Paste Key > Add SSH Key
ssh -T git@github.com

git config --global user.name "<your_name>"
git config --global user.email "<your_email_address>"
git config --global color.ui true
cat ~/.gitconfig

# How to use Git 
# - try every line at the command line 
# - lines preceeded by "#" are comments or headers
git help
git help -a
git help -g
git help attributes
q
git help everyday
q
git help glossary
q
git help ignore
q
git help modules
q
git help revisions
q
git help tutorial
q
git help workflows
q
git help init
q
git init --help
q
git help add
q
git add --help
q
git help commit
q
git commit --help
q
git help status
q
git status --help
clear

#CreatingANewRepository
# Github.com > new repository > ProjectName
# Click Create repository

mkdir ProjectName && cd ProjectName
git init                # mkdir .git and add important files
ls
ls -a
cd .git
tree
cat description
nano description
ProjectName; a description of ProjectName
Ctrl+X
Y
nano description
cd ..
git status
git diff
git diff --cached
git diff HEAD
git commit -m "This does nothing when there is nothing to commit"
git log
git log --oneline
git log --merges
git log --graph
clear

git remote add origin https://github.com/<username>/ProjectName
git remote add origin git@github.com:<username>/ProjectName
git pull origin master
clear

#KeepingFilesAndDirectoriesPrivate
cat .gitignore
mkdir DirectoryNotToBeShared
echo "DirectoryNotToBeShared/" >> .gitignore
cat .gitignore
touch FileNotToBeShared.extension
echo "FileNotToBeShared.extension" >> .gitignore
cat .gitignore
ls
ls -a
git status
git add .gitignore
git diff
git diff --cached
git diff HEAD
git commit -am "Created list of Files and Directories for git to ignore"
git log
git log --oneline
git log --merges
git log --graph
git status
git add DirectoryNotToBeShared/
git add FileNotToBeShared.extension
git status
clear

touch File1InThisDirectory.extension 
touch File2InThisDirectory.extension 
touch File3InThisDirectory.extension
touch File4InThisDirectory.extension
ls
tree
mkdir Directory1
touch Directory1/File1InDirectory1.extension
touch Directory1/FileNInDirectory1.extension
mkdir Directory2
touch Directory2/File1InDirectory2.extension
touch Directory2/python_file.py
touch Directory2/java_file.java
touch Directory3/html_file.html
mkdir Directory3 && cd Directory3 && pwd
mkdir ChildOfDirectory3 && cd ChildOfDirectory3
mkdir ChildOfChildOfDirectory3 && cd ChildOfChildOfDirectory3
pwd
touch file1.txt file2.txt file3.txt fileN.txt
ls
cd ../.. && pwd
mkdir DirectoryN
touch DirectoryN/FileInDirectoryN.extension
ls
tree
clear 

#AddingFilesAndDirectories to Local Repository
git status
tree
git add File1InThisDirectory.extension
git status
git add Directory1/File1InDirectory1.extension Directory1/FileNInDirectory1.extension
git status
git add Directory2/File1InDirectory2.extension
git status
git add Directory3/
git status
git add -A
git status
tree
git diff
git diff --cached
q
git diff HEAD
q
git commit -am "Added new files"
git log
git log --oneline
git log --graph
git commit --amend -m "Added new Ffiles and Directories"
git log
git log --oneline
git log --merges
git log --graph
git push -u origin master
git diff
clear

#Branching
git status
git branch -a
git branch a_new_branch
git branch -a
git branch -d a_new_branch
git branch -a
git branch an_old_branch_name
git branch -a
git branch -m an_old_branch_name a_new_branch_name
git branch -a
git branch a_branch
git branch -a
git checkout a_branch
git branch -a
git status
git checkout master
git status
git branch -a
git checkout a_new_branch_name
git branch -a
git status
git checkout -b a_new_branch
git branch -a
git status
git checkout master
ls
tree
git branch -a
git push origin a_branch
git branch -a
git push origin a_new_branch
git branch -a

#MergingChanges
git checkout a_branch
touch file_from_a_branch.extension
mkdir new_directory_from_a_branch
touch new_directory_from_a_branch/file_in_new_directory_from_a_branch.extension
git add -A
git commit -am "Added New File and Directory in a_branch"
git push origin a_branch
git diff
git diff master
git checkout master
git diff remotes/origin/master
git diff a_branch
git merge a_branch
git diff
git diff a_branch
git diff remotes/origin/master
git push origin master

git checkout a_new_branch
git branch -a
git diff master
git merge master
nano FileInThisDirectory.extension
1 genius Idea to test in a_new_branch
ctrl+X
y
git status
git add -A
git commit -am "1 Genius Idea tested in a_new_branch"
git diff master
git diff remotes/origin/a_new_branch
git push origin a_new_branch
git checkout master
git merge --no-ff a_new_branch
Had a Genius idea and tested it in a_new_branch
# save and exit
git diff
git diff a_new_branch
git diff remotes/origin/master
git status
git push origin master
git log
git log --oneline
git log --merges
git log graph

#Tagging
git tag
git tag -a v0.1 "Beta Test version 1"
git tag
git tag -a v0.1 -m "Beta Test version 1"
git tag
git tag -a v1.1 -m "Version 1.0 revision 1"
git tag
git tag v2.0 -m "Version 2.0"
git tag
git tag vN.M -m "Version N revision M
git tag
git tag any_tag -m "Description for the Tag"
git status
clear 

git show
git show v0.1
git show v1.1
git show v2.0
git show vN.M
git show any_tag
git show non_existent_tag
clear

git push origin v0.1
git push origin vN.M
git push origin --tags

git log
git log --oneline
git log --merges
git log --graph

# Cloning a repository
git clone <git_URL>
git clone --depth <N> <git_URL>
git clone -b <branch_name> <git_URL> --single-branch
