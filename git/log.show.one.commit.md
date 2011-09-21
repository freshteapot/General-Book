# Show one commit via log with the commit id.

COMMIT can be blank or a commit id (sha-1)

Display the log.
```
    git log COMMIT -1 --name-only
```

This will list just the files
```
    git log COMMIT -1 --name-only --pretty=format:"" | grep "[^\s]"
```
 
## Searched for
* show files changed for a commit


## Links
* http://stackoverflow.com/questions/424071/how-do-i-list-all-the-files-for-a-commit-in-git