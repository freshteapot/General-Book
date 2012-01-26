#Delete lines starting with.

I wanted to be able to delete lines that start with "INSERT INTO" whilst working with a ".sqlite" file.

After dumping the database using:

echo ".dump" | sqlite3 db.sqlite > db.sql

I opened up "db.sql" in vim.

Stripping the database back to just what was needed to create the database, I found myself wondering how to delete all lines starting with "INSERT INTO".

## The answer
    g/^INSERT INTO/d

## Search
- vim delete all lines starting with

## Links
- http://vim.wikia.com/wiki/Delete_all_lines_containing_a_pattern