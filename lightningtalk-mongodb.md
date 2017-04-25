# [MongoDB Server](https://www.mongodb.com/what-is-mongodb)

<hr>
### What is MongoDB?

- Open-source
- Document-oriented database
- ~~Object Relational Mapping~~
- data storage: JSON-like documents
````
{
   "_id" : ObjectId("54c955492b7c8eb21818bd09"),
   "address" : {
      "street" : "2 Avenue",
      "zipcode" : "10075",
      "building" : "1480",
      "coord" : [ -73.9557413, 40.7720266 ]
   }
````
- scalability
- stores documents in collections; analogous to tables in relational databases
- documents in collection: unique ````_id```` field as primary key

<hr>
### MongoDB SetUp
##### 1. Download MongoDB
Starting out with homebrew...

````
brew update
brew install mongodb
````

##### 2. Specify A Data Directory
Create directory where ````mongod```` process will write data...
````
mkdir -p /data/db
````
If specifying another directory, you must specify the directory in the ````dbpath```` option when starting the ````mongod```` process later on...

##### 3. Start up MongoDB Server
In a new terminal tab...
````
mongod
````

##### 4. Start up MongoDB Shell
In another terminal tab...
````
mongo
````

<hr>
### Useful Tips
_1. When naming a database, you cannot use:_

````/ \ . * < > " | ? $ :````

_2. We can run JavaScript code directly in our shell._

_3. Show all databases:_

```` show dbs ````

_4. Show current database:_

```` db ````

_5. Make a new database:_

```` use new_db_name ````

<hr>
### Documents in Databases:
##### Making a document:
````
dog = {
  "name" : "Woofers",
  "fur color" : "spotted",
  "age" : "2",
  "cuteness" : "extreme"
}
````
##### Adding doc to database:
````
db.test.insert(dog)
````
##### Viewing info in database:
````
db.test.find()
db.test.find().pretty()
````
##### I want my dog to have a list of treats he can have:
````
dog.treats = []
db.test.update({"name" : "Woofers"}, dog)
````
````
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
````
##### Delete information:
````
db.test.remove{"name" : "Woofers"}
````
##### What Values can we store?
````
null : {"name" : null}
boolean : {"over20" : true}
number : {"height" : 6.25} (64 bit float numbers)
string : {"address" : "123 Main Street"}
{"grades" : ["a", "b", "c", "d", 123]}
{"streetregex" : /^[A]}
{"info" : {"name" : "Sue Smith"}}
randomdata = {"name" : null ....}
````


<hr>
#### Resources
Youtube Tutorial:

[MongoDB Tutorial Series on YouTube by Derek Banas](https://www.youtube.com/watch?v=-0X8mr6Q8Ew)

MongoDB Documentation:

[MongoDB Ruby Documentation on Getting Started](https://docs.mongodb.com/ruby-driver/master/quick-start/)
