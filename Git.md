# Git Cheat Sheet

Git is a widely used version control system for software development which 
emphasises speed, data integrity and support for distributed, non-linear
workflows -- [source](https://en.wikipedia.org/wiki/Git_%28software%29).

> This is based on a number of sources but especially the excellent 
> http://git-scm.com/book written by Scott Chacon and Ben Straub and 
> published by Apress.
> Anything in angled brackets needs to be replaced with something suitable.
> A "#" indicates the start of a comment - so ignore the rest of the line.

> E.g. $ git help \<command\> might mean $git help *config*

### Setting User Options
```
$ git config --global user.name "Stephen Moon"
$ git config --global user.email stephen@logicalmoon.com
$ git config --global core.editor "'<path to your editor>'" 
```

### Viewing User Options
```
$ git config --list
```

### Starting a New Repository
```
$ git init # inside the directory you want to begin using source control with
```

### Cloning (Copying) a Repository
```
$ git clone <url to repository> # e.g. https://github.com/s-moon/CheatSheets.git
$ git clone <url to repository> <your choice of directory name> # e.g. https://github.com/s-moon/CheatSheets.git CheatSheetsGalore
```

### Viewing the Status of Your Repository
```
# long form
$ git status 

# short form of the same (see: http://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository#Short-Status)
$ git status --short 
```

### Ignoring Files in your Repository
```
$ cat .gitignore
*.[oa] # ignore everything ending in o or a e.g. file.oa
*~ # ignore all files which end in the tilde character
# see (http://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository#Ignoring-Files)
```

### Getting Help
```
$ git help <command>
```

### Adding Files
```
# Add a specific file
$ git add <file path>

# Add all files in current directory
$ git add .

# Adding files one by one (use y, n or q to end)
$ git add -p
```

### Viewing Your Unstaged Commits
```
$ git diff
```

### Undoing an Edit to a File
```
$ git checkout --- <file you want to lose the edit for>
```

### Committing a Change
```
$ git commit # commit message will be required
$ git commit -m "This is my commit message" # commit message supplied
$ git commit -a # stage all modified (but not new) files and commit them in one.
```

### Viewing Your Staged Commits
```
$ git diff --staged
```

### Pushing Changes to Your Remote Repository
```
$ git push origin
$ git push origin master # use this if it complains about branches/which branch
```

### Adding remote repositories
```
$ git remote add <name of remote> <url of remote>
```

### Listing remotes
```
$ git remote -v
```

### Making your remotely forked repository match the original
```
$ git pull upstream master
$ git push origin master
# NB - this assumes you have origin pointing to your forked repository
# and that upstream points to the source repository.
```

### Removing Files
```
$ git rm PROJECTS.md # removes from the file system AND from staging
```

### Renaming Files
```
$ git mv file_from file_to
```

### Viewing Commit History
```
$ git log

# show difference AND limit to last two entries
$ git log -p -2	

$ git log --pretty=oneline # one line version
```

### Undoing a Commit Message
```
# this will allow you to re-do your commit message
$ git commit --amend 

$ git add <file-that-I-forgot>

# a second file is added and included in the original commit
$ git commit --amend 
```

### Unstaging a Commit
```
$ git reset HEAD <file to undo>
```

### Undoing a File Modification
```
$ git checkout -- <file to undo> # this will revert a file back to before you modified it

# remove all changes
$ git co --
```

### Creating a branch and switching to it
```
$ git checkout -b <branch-name>
```

### Deleting a branch
```
$ git branch -d <branch-name>
```

### Switching between branches
```
$ git co -
# repeat to switch back to previous branch

or
$ git checkout <branch-name>
```

### Merging a branch with master
Let's say thay you have a branch called master (you will) and
another which is named <branch name>. <branch name> already
contains committed changes that you want to merge back into 
master.
```
$ git checkout master
$ git merge <branch-name>
```

### Adding a Submodule
```
$ git submodule add <git-reference> # e.g. https://github.com/zendframework/zf1.git
```

Written by Stephen Moon (stephen@logicalmoon.com)
