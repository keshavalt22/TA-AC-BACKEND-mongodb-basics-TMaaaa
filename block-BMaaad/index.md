writeCode

Write command to

- List collections from a database.
> show dbs
- create a new collection in your country database which you created recently.
> db.createCollection('delhi')

Write code to:-

- crate a database named `weather`
> use weather

- create a capped collection named `temperature` with maximum of 3 documents and try inserting more than 3 to see the result.
> db.createCollection("temperature",{capped:true,size:10000,max:1000})

> db.temperature.insert({title : 'heat'})

> db.temperature.insert({title : 'cold'})

> db.temperature.insert({title : 'freezing'})

> db.temperature.insert({title : 'warm'})
- create a simple collection named `humidity`
> db.createCollection('humidity')

- check whether `temperature` collection is capped or not ?

> db.temperature.isCapped()

- Delete `humidity` collection and then the entire database(weather).
> db.humidity.remove()