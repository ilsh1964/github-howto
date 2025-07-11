# Working With Git (Locally):

## Creating a brand new git repository
```
$ cd  PROJECT_DIR
$ git --version                               # Print Git version
$ git config --global user.name "YOUR_NAME"
$ git config --global user.email "YOUR_EMAIL"
$ git config --global core.editor "vim"       # Change the default editor
$ git config --list                           # Show your config
```

## Working with git
```
$ git init                                    # Create a brand new Git repository in this directory
$ git add .                                   # Add all changes in the current directory to the stage area
$ git add -A                                  # Add all changes (removed, modified, sub-dir, new) files to the staging area
$ git add *.txt                               # Add all *.txt files to the stage area
$ git add FILENAME                            # Add FILENAME again

$ git rm --cached FILENAME                    # To untrack FILENAME (remove from staging area)
git restore --staged index.html               # To untrack FILENAME (remove from staging area)

$ git rm -f FILENAME                          # Delete FILENAME from os
$ git mv XXX YYY                              # Rename filename XXX to YYY

$ git status                                  # What files have been changed
$ git status -s                               # Show what has been changed in compact list

$ git commit -m "My First Commit"             # Commit
$ git commit -a -m "some msg"                 # Add files + commit in one command

$ git checkout SHA_NUMBER                     # go to previous version of the file
```

## Git reset
```
$ git reset FILENAME                          # Remove file from staging area
$ git reset                                   # Remove all files from staging area

$ git log                                     # write the desire commit-log-id
$ git reset --soft commit-id                  # Keeps all changes made after that commit in the staging area
$ git reset --hard commit-id                  # Discards all changes in the staging area and in the working directory that happened after that commit
$ git reset commit-id (eqvivalent to --mixed) # Unstages all files from the staging area, Keeps your working directory unchanged)
```

## Git stash
```
$ git stash                                   # Save all current changes
$ git stash list                              # Get list of all stashes
$ git stash pop                               # Pop last stashed files

```

## Git diff
```
$ git diff                                    # See changes on files since last commit
```

## Git checkout
```
$ git log --pretty=oneline
    b900c412b20d0ae61e4f81f3ec60766bce8f107a file1.txt: Add line 3
    2f52aa202095e16a660a5c479524622f6e3c36d2 file1.txt: Add line 2
    3c2df3030561f5a49defb108441a7dd850ac1857 Adding file1.txt

$ git checkout 2f52aa202095e16a660a5c479524622f6e3c36d2

$ git log --pretty=oneline
    2f52aa202095e16a660a5c479524622f6e3c36d2 file1.txt: Add line 2
    3c2df3030561f5a49defb108441a7dd850ac1857 Adding file1.txt

$ git checkout master                         # Return to the master branch

$ git log --pretty=oneline
    b900c412b20d0ae61e4f81f3ec60766bce8f107a file1.txt: Add line 3
    2f52aa202095e16a660a5c479524622f6e3c36d2 file1.txt: Add line 2
    3c2df3030561f5a49defb108441a7dd850ac1857 Adding file1.txt

$ git checkout file1.txt                      # return file1.txt from last commit
```

## Git Log
```
$ git log                                     # Shows all previous commit messages in reverse order
$ git log --pretty=oneline                    # Shows commits on one line
$ git log --oneline                           # Compact list of commits
$ git log --since=1.weeks                     # Show only changes in the last week
$ git log --since="2014-04-12"                # Show changes since this date
```

## Branching and Merging
```
$ git branch                                  # Show all brances
$ git branch proj_v2                          # Create a new brand called proj_v2
$ git checkout proj_v2                        # Working with the new branch
$ git checkout -b proj_v2                     # Create a new branch and jump to it
$ git checkout master                         # Go to the master branch - without file1.txt
$ git merge proj_v2                           # Merge file1.txt from proj_v2 branch
$ git branch -d proj_v2                       # Deleting merge  branch
```

## .gitignore  (must be in project dir - not in .git)
```
*.apk
.ThisFile
ThisDir/
```


# Github:

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


## Tags
    $ cd project_dir
    $ git tag                              # To show all tags
    $ git tag -a v1.01 -m 'version 1.01'   # To add new tag (follow with the next command)
    $ git push --tags                      # To push the new tag to github.com
    $ git tag --delete v1.1
    $ git tag -d v1.01                     # To delete tag (follow with the next command)
    $ git push origin :refs/tags/v1.01     # Update github.com with previous tag deleting
    $ git tag -l v1.0*                     # Search tags via wildcard
    $ git show v1.01                       # Show tag version v1.01

## Diff
    $ git diff v1.0 v1.01                  # Show diff between tag version v1.0 & v1.01


# FAQ

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

## Delete Your Commit History (clean-up the repo)
```
git checkout --orphan temp_branch
git add -A
git commit -m "Initial commit"
git branch -D main
git branch -m main
git push --force origin main
```

## Stop Monitoring A File
```
git rm --cached <file_name>  (--cached: do not delete the file locally)
Add the file to .gitignore
git commit -m "Stop tracking <file_name>"

Example:
Stop monitoring: .local/share/fish/fish_history
add .local/share/fish/fish_history to .gitignore

if the file is already tracked by Git:
git rm --cached .local/share/fish/fish_history

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
