## start
start mongodb server
```shell
mongod
```
should keep the terminal window and open a new terminal window
```shell
mongodb
```
and this window becomes a mongodb terminal   
to clear the screen
```
cls
```
## some basics
to see existing db
```
show dbs
```
switch to a specific db (will create a new one on the fly if it does not exist)
```
use <db_name>
```
insert one document to a collection (can be created on the fly)
```
db.<collection_name>.insertOne({<key_value_pairs>})
```
mongodb will automatically generate an id for each inserted document   
```
db.<collection_name>.find()
```
will show all documents under the collection
```
db.<collection_name>.find().pretty()
```
show in a prettier way
