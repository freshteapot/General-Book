I want to drop the indexes and then import new ones.

DB_FILE "test.sqlite"
DB_NAME "test_db"

sqlite3 Resources/DB_FILE.sqlite .dump

CREATE UNIQUE INDEX uniq_item ON item_text (data);
CREATE UNIQUE INDEX uniq_key ON app_settings ( key );
CREATE UNIQUE INDEX uniq_item_note ON item_note (item_id_from, item_id_to);
CREATE UNIQUE INDEX index_item_note_item_id ON item_text (ID);
CREATE UNIQUE INDEX index_items_item_id ON items (ID);
CREATE UNIQUE INDEX uniq_list_items ON list_items(list_id, item_id);
CREATE UNIQUE INDEX uniq_reminder ON reminder(item_id);


Code below - Edit to make it not specific to wordpoke
~~~

Ti.include("../lib/database.js");

var config = {
        "file" : "DB_FILE",
        "name" : "DB_NAME"
};
var db = new Database(config);


var sql = 'SELECT "DROP INDEX " ||name||";" as name FROM sqlite_master WHERE type=\'index\';';

var results = db.fetchAll(sql);
var queries = db.resultAsSingleColumn(results,'name');
Ti.API.info(queries);

if( queries != null){
    var size = queries.length;
            
    for(i=0;i<size;i++) {
        var sql = queries[i];
        Ti.API.info(sql);
        db.query(sql); 
    }   
}
/*
 * Do sqlite3 database .dump 
 * You could further throw in a grep to extract out CREATE UNIQUE INDEX
 */

db.query("CREATE UNIQUE INDEX uniq_key ON app_settings ( key );");

/*
 * Output the new list - semi confirmation. Makes you feel good.
 */
var sql = 'SELECT name FROM sqlite_master WHERE type=\'index\';';
var results = db.fetchAll(sql);
var queries = db.resultAsSingleColumn(results,'name');
alert(queries.join("\n"));



~~~


SELECT "DROP INDEX (" ||name||");" FROM sqlite_master WHERE type='index';

This will give us each index on its own line;

Then we just sift thru them.

The code