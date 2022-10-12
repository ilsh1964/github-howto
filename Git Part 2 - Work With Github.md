# Working With Github:

## Creating new project
    $ Create a new repository in github.com and paste it's instruction:
    $ cd My-NEW-Repository
    $ git init
    $ git add README.md or git add .
    $ git commit -m "First Commit"
    $ git remote add origin https://github.com/ilsh1964/My-NEW-Repository.git
    $ git push -u origin master


## Deleting files on github
    $ git add . -A
    $ git commit -m "removed some files"
    $ git push origin master


## Updating git with updated files
    $ git add My_Changed_File  or git add .
    $ git commit -m "My commit explanation"
    $ git push


## Get changes FROM GitHub to your machine
    $ git checkout
    $ git pull


## Tags and Diff
    $ cd project_dir
    $ git tag                              # To show all tags
    $ git tag -a v1.01 -m 'version 1.01'   # To add new tag (follow with the next command)
    $ git push --tags                      # To push the new tag to github.com
    $ git tag -d v1.01                     # To delete tag (follow with the next command)
    $ git push origin :refs/tags/v1.01     # Update github.com with previous tag deleting
    $ git tag -l v1.0*                     # Search tags via wildcard
    $ git show v1.01                       # Show tag version v1.01
    $ git diff v1.0 v1.01                  # Show diff between tag version v1.0 & v1.01


## Why is Git always asking for my password?
    $ Add ~/.ssh/id_rsa.pub to your github account (menu->SSH Keys)
    $ git remote set-url origin git+ssh://git@github.com/username/reponame.git


## Cloning github project to your local machine
    $ cd Dropbox/Git dir
    $ git clone git@github.com/…git


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

## REAMRKS
```
- Every repository should include README.md, LICENSE.md, and .gitignore
- Good source: http://www.linuxandubuntu.com/home/getting-started-with-github
- ssh -T git@github.com                     \* To check the ssh key against github
- Branching allow you to create a separate working copy of your code
- Merging: Allow you to merge branches together
- Cloning: Another developer can copy your Git-Hub project
- git clone <url>  .
- git remote -v  show information about git
- git branch -a
- git pull bring all changes from last pull
```
