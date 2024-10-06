# Working With Github:

## Creating new project
    $ Create a new repository in github.com and paste it's instruction:
    $ mkdir my-project && cd my-project
    $ git init
    $ git add -A (or add specific files: git add README.md)
    $ git commit -m "First Commit"
    $ git branch -M main
    $ git remote add origin git@github.com:ilsh1964/my-project.git
    $ git push -u origin main
    $ git push -f origin main
        if you have an error and you want to force the push command
     
        

## Updating git with new\updated files
    $ git add My_Changed_File \ git add -A
    $ git commit -m "My commit explanation"
    $ git push origin master


## Deleting files on github
    $ git add -A
    $ git commit -m "removed some files"
    $ git push origin master


## Get changes FROM GitHub to your machine
    $ git checkout (command is used to switch, and optionally create, to a branch.
    $ git pull (combination of two commands: "git fetch" which downloads changes, "git merge" which merge changes 
   
## Delete old Github commits (clean-up the repo)
    $ git clone git@github.com:ilsh1964/repo_name
    $ cd repo_name
    git checkout --orphan new_branch
    git add .
    git commit -m "First commit"
    git branch -D main
    git branch -m main 
    git push -f origin main

## Tags and Diff
    $ cd project_dir
    $ git tag                              # To show all tags
    $ git tag -a v1.01 -m 'version 1.01'   # To add new tag (follow with the next command)
    $ git push --tags                      # To push the new tag to github.com
    $ git tag --delete v1.1
    $ git tag -d v1.01                     # To delete tag (follow with the next command)
    $ git push origin :refs/tags/v1.01     # Update github.com with previous tag deleting
    $ git tag -l v1.0*                     # Search tags via wildcard
    $ git show v1.01                       # Show tag version v1.01
    $ git diff v1.0 v1.01                  # Show diff between tag version v1.0 & v1.01


## Why is Git always asking for my password?
    $ Add ~/.ssh/id_rsa.pub to your github account (menu->SSH Keys)
    $ git remote set-url origin git+ssh://git@github.com/username/reponame.git


## Cloning github project to your local machine
    $ git clone git@github.com/…git

## Cloning a Private github repo (using ssh key)
    $ git clone git@github.com:ilsh1964/my-config.git


## BRANCH
```
Branches are a way of working on various versions of a single repository simultaneously.
By default, any single repository created is assigned a branch called MASTER and it is considered
the final branch.

To make a branch after creating the repository:
1. Go to your new repository by clicking on the repository name
2. Click on the “Branch-Master” button at the top to see a drop-down menu with a blank field for
   filling the branch name.
3. Enter the branch name
4. Press “Enter” or click on the blue “create- branch” box
5. By now two branches have been created; master and your new name branch
```

## Delete Your Commit History
```
git checkout --orphan temp_branch
git add -A
git commit -m "Initial commit"
git branch -D main
git branch -m main
git push --force origin main
```

## REAMRKS
```
- Every repository should include README.md, LICENSE.md, and .gitignore
- Branching allow you to create a separate working copy of your code
- Merging: Allow you to merge branches together
- Cloning: Another developer can copy your Git-Hub project
- git pull: bring all changes from last pull
- Good source: http://www.linuxandubuntu.com/home/getting-started-with-github
```
