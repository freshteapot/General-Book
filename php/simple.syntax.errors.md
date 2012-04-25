#

Find files (and lines of code) which have small errors in them.

1st error:
;;

```
find . -type f -name "*.inc" | xargs -I {} grep -Hn ';;$' {}
```

At first I thought it was due to our company, yet then I noticed third party libraries making these mistakes.

No idea what the downside is of having ";;".
