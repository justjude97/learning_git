# How Git Works
source: https://www.youtube.com/watch?v=3fUbBnN_H2c

1. working directory
    * various files for building application
    * CSS/JS/HTML, .cpp, .py, ...
2. Staging Area
    * *git add* to add source files to staging area
    * staging area holds changed files you want to commit to commit history
3. Commit History
    * keeps track of changes made to a project over time
    * can have a bunch of **commits**, which are "save points" for a project
    * commit history sent to remote server (github, bitbucket, gitlab, etc) by *git push*

## Commands
* *git add* - adds source files to staging area
    * git add . adds all files from current directory, downwards
    * git add -A adds all changed files in the working directory
* *git rm* - removes files from the working tree and from the index
    * --cached amkes the command remove pathes from the index only
* *git commit* - adds files in staging area to a commit
    * -m <msg>, --message=<msg> - use the given <msg> as the commit messsage. multiple -m commands are concatenated
    * --interactive or --patch lets you decide which files should be part of the commit by a file-by-file basis
    * -a, --all - automatically stage files that have been modified or deleted. new files you haver not told git about are not affected
* *git push* - sends commits to repository
* *git pull* - pulls branch of project from server
* *git diff* - shows differences between the current working directory and the commit
    * can be used to compare commit hashes *git diff {hash 1} {hash 2}*
* *git branch* - list and modify branches
    * *git branch -r* shows branches of remote
    * *git branch {name}* creates branch {name}
* *git checkout* - switch branches or restore working tree files

## Repositories
* contains a collection of files of various different versions of a project
* need to initialize a repository with *git init*
* copy an existing project form a remote repostory with *git clone*

## HEAD vs Wrokign Tree vs Index vs Staging Area
* source: https://stackoverflow.com/questions/3689838/whats-the-difference-between-head-working-tree-and-index-in-git
* HEAD is the commit at the tip of the branch
* Workspace is the directory tree or (source) files that you see and edit
    * working tree is the state of the files at *checkout*
* Index is a single, large, binary file (.git/index) which lists all the files in the current branch, their sha1 checksums, timestamps, and the file name
* local repository is a hidden director (.git) including an objects directory containg all versions of every file in the repo (local branches and copes of remote branches as a compressed blob file)

## Commits
* a "save point" for a project, recording changes made to that project
* a commit message is important to convey what a change does
    * to change the message of a commit you can use git commit --amend

## Branches
* [branches in a nutshell](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)
* branches allow you to make changes to source code without messing up the mainline during development
    * git branching is lightweight and allows for fast switching
* remember: git stores changes as a series of **snapshots** meaning that a commit object contains a pointer to the snapshot of the object you changed


## Other Sources:
* https://nfarina.com/post/9868516270/git-is-simpler
* https://git-scm.com/book/en/v2