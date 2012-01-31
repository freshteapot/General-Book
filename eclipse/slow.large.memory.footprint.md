# Things to do when memory footprint rises and eclipse starts going slow.

## Remove "index".
I am not 100% sure what the knock on effects are.
However, after deleting the "index" file, eclipse rebuilds it.

- Close eclipse
- mv (not delete) 
- Open eclipse

From

    1610612784 Jan 31 09:02 model.index.db
    1.5G Jan 31 09:02 model.index.db
To

    100663344 Jan 31 09:14 model.index.db
    96M Jan 31 09:14 model.index.db

Even tho the heap is reporting 404m and memory footprint is 500mb.
The actual heap in use claims 203M.

This was the first loading of eclipse, so I speculate this increases memory footprint due to reindexing.
After closing and opening. Heap reports 350m, use 241m and footprint is 440m

```
cd {workspace}/.metadata/.plugins/org.eclipse.dltk.core.index.sql.h2 
mv model.index.db ../
```
Remove when happy with the "move.index.db" that you moved so eclipse would rewrite it.


## Links
- [Great tip for locating the database files](http://www.nwiresoftware.com/blogs/nwire/2010/09/five-tips-speeding-eclipse-pdt-and-nwire)
