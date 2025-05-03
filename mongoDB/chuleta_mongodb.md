# show data bases in existence at the server

show dbs

# Use some data base with name dataBaseName

use dataBaseName

# show collections in a data base

show collections

# Show the records in a collection 

db.collectionName.find.pretty()

# Insert a record in a collection 

db.collectionName.insertOne({"name":"Arepa3000", "description":"Pura música"})

# Delete a record with a given key:value

db.collectionName.deleteOne({key:"value"})

# Delete a collection with a collection name 

db.collectionName.drop()

# Delete a data base

db.dropDatabase()

# Run mongodb in a given IP and with .mongo/data as regiters directory.

mongod --dbpath=.mongo/data/ --bind_ip 192.168.1.129
mongod --dbpath=/directorio/file --bind_ip 192.168.23.16
ip_bind is a param for to give a IP to the mongo server

