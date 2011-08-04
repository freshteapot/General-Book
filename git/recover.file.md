# Recovering a file when you overwrite it with another file.

I have realised that I have saved a file to another filenam and lost the data.

After renaming the file correctly, here is how I got the data back from the last commit. (Thank you version control)

```
git log --name-only
```

Search for the file if you know it.

"Resources/setup/update.tables.js"

When found, look to the commit reference  "3c93399ea823d33b9748e606a845a751ac186682"

Using the <commit>:<path>, I save it back :)

```
git show 3c93399ea823d33b9748e606a845a751ac186682:Resources/setup/update.tables.js > Resources/setup/update.tables.js
```