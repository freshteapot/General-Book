#How to update local repository with remote repository in git

```
git remote update
```

Reading the man page there was an interesting option. prune.
```
git remote prune --dry-run origin
```
This will not prune anything, yet will display what it would prune on the remote repository "origin".



##Man Page
man git-remote

##Searched for
* git remote update

##Links
http://www.kernel.org/pub/software/scm/git/docs/git-remote.html 