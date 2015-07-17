Title: Environments
ms.ContentId: C777EDBC-C56E-4F2E-B017-B75C907BC344

##Git
Prerequisite: [Git](http://msysgit.github.io/) is installed on your machine

### Getting a Git Repository
You can get a Git project using two main approaches:

* Create a new Git repo and import it into Git
* Clone an existing project from a server

### Initializing a Git Repository 
Go to a project's directory and type
```bash
$ git init
```
This creates a new subdirectory named .git that contains all of your necessary repository files - a Git repository skeleton. At this point, nothing in your project is tracked yet.
If you want to start version controlling your project, you should initialize commit. **git add** commands specify the files you want to track, follows by a commit:
```bash
$ git add *.cs
$ git add README
$ git commit -m 'initial project version'
```

### Cloning an Existing Repository
```bash
$ git clone [url]
```

### Git Basic Command
####**git add**

Add file contents to the index
####Synopsis
```bash
'git add' [-n] [-v] [--force | -f] [--interactive | -i] [--patch | -p]
[--edit | -e] [--[no-]all | --[no-]ignore-removal | [--update | -u]]
[--intent-to-add | -N] [--refresh] [--ignore-errors] [--ignore-missing]
[--] [<pathspec>...]
```
####Examples
```
//Adds content from all *.md files under **Content** directory and its subdirectories
$ git add Content/*.md

//Adds all files under current directory
$ git add --all
```
####See Also
[git-add](http://git-scm.com/docs/git-add/)

####**git rm**

Remove files from the working tree and from the index
####Synopsis
```bash
git rm [-f | --force] [-n] [-r] [--cached] [--ignore-unmatch] [--quiet] [--] <file>...
```
####Examples
```
//Remove all *.md files from the index that are under **Content** directory and any of its subdirectories
$ git rm Content/*.md

//Force remove all files matches the wild card expression under **Content** directory, but not under its subdirectories
$ git rm -f api-*.md
```
####See Also
[git-rm](http://git-scm.com/docs/git-rm/)

####**git mv**

Move or rename a file, a directory, or a symlink
####Synopsis
```bash
git mv <options>... <args>...
```
####Examples
```
//Force move a file from <source> to <destination>
$ git mv -f <source> <destination>
```
####See Also
[git-mv](http://git-scm.com/docs/git-mv/)

####**git commit**

Record changes to the repository
####Synopsis
```bash
'git commit' [-a | --interactive | --patch] [-s] [-v] [-u<mode>] [--amend]
[--dry-run] [(-c | -C | --fixup | --squash) <commit>]
[-F <file> | -m <msg>] [--reset-author] [--allow-empty]
[--allow-empty-message] [--no-verify] [-e] [--author=<author>]
[--date=<date>] [--cleanup=<mode>] [--[no-]status]
[-i | -o] [-S[<key-id>]] [--] [<file>...]
```
####Examples
```
//Record all changes with given message
$ git commit -m 'message here'
```
####See Also
[git-commit](http://git-scm.com/docs/git-commit/)

####**git pull**

Fetch from and integrate with another repository or a local branch
####Synopsis
```bash
'git pull' [options] [<repository> [<refspec>...]]
```
####Examples
```
//Update the remote-tracking branches from the repository you cloned from, then merge one of them into your current branch 
$ git pull, git pull origin

//Merge into the current branch from the remote branch 'next'
$ git pull origin next
```
####See Also
[git-pull](http://git-scm.com/docs/git-pull/)

####**git push**

Update remote refs along with associated objects
####Synopsis
```bash
'git push' [--all | --mirror | --tags] [--follow-tags] [-n | --dry-run] [--receive-pack=<git-receive-pack>]
[--repo=<repository>] [-f | --force] [--prune] [-v | --verbose] [-u | --set-upstream]
[--force-with-lease[=<refname>[:<expect>]]]
[--no-verify] [<repository> [<refspec>...]]
```
####Examples
```
//Works like **git push <remote>**, where <remote> is the current branch's remote(or origin, if no remote is configured for the current branch)
$ git push

//push all updates to remote/origin branch. add upstream (tracking) references
$ git push -u origin --all
```
####See Also
[git-push](http://git-scm.com/docs/git-push/)

####**git status**
```
//Show the working tree status
$ git status
```
####See Also
[git-status](http://git-scm.com/docs/git-status/)

####**git diff**
```
//Show the changes between commits & working tree etc
$ git diff
```
####See Also
[git-diff](http://git-scm.com/docs/git-diff/)

