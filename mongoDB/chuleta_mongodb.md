# Data folder

mongod --dbpath=data

# Mostrar las bases de datos existentes

show dbs

# Usar una base de datos particular

use dataBaseName

# Mostrar las colecciones de una base de datos

show collections

# Ver los records de la colección 

db.collectionName.find.pretty()

# Insertar un record en una colección 

db.collectionName.insertOne({"name":"Arepa3000", "description":"Pura música"})

# Borrar u record con un key:value dado en

db.collectionName.deleteOne({key:"value"})

# Borrar una colección

db.collectionName.drop()

# Borrar una base de datos

db.dropDatabase()


