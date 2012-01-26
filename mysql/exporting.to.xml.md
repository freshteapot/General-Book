#Export a query to xml and parse it thru xmllint.


###Swap
* DB_NAME with your database name.
* QUERY with your sql query.

```
mysql -uez -h127.0.0.1 DB_NAME -e "QUERY" --silent -N | sed -e 's#>\\n#>#g' | xmllint --format -
```

In this case the data needed to parsed to remove the extra end of line character.

If you are thinking of outputing blob data you will need to use:
```
--hex-blob
```

##Links

* http://dev.mysql.com/doc/refman/5.5/en/mysqldump.html#option_mysqldump_xml
* http://metaoptimize.com/blog/2009/10/14/use-flag-xml-when-you-run-mysqldump/
* http://dev.mysql.com/doc/refman/5.5/en/mysqldump.html#option_mysqldump_hex-blob
