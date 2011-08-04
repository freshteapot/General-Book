#How to drop an index in sqlite


http://www.sqlite.org/images/syntax/drop-index-stmt.gif

Concat in sqlite is note concat() but ||

###List an sql created output to then be self ran by your database handler
```sql
    SELECT "DROP INDEX (" ||name||");" FROM sqlite_master WHERE type='index';
```

```sql
DROP INDEX (
    SELECT name FROM sqlite_master WHERE type='index'
);
```

##Searched for
drop index sqlite
sqlite run select query

##Link(s)
http://www.sqlite.org/lang_dropindex.html
