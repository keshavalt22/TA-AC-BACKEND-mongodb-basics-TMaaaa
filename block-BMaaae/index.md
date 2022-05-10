writeCode

Write code to:-

- create a database named `sports`.
- list all databases present in local mongod server.
- create 3 collections named `cricket`, `football`, `TT`
 in sports databse.
 > db.createCollection('cricket') 
 > db.createCollection('football')
 > db.createCollection('tt')
- add multiple players in those collections which should have fields like `name`, `age` and `email` and `bid_price`.
- list all collections in sports database.
> db.cricket.insertMany(players)
> db.football.insertMany(players) 
> db.tt.insertMany(players) 

- rename `TT` collection to `tennis`.
> db.tt.renameCollection('tennis') 
- create a capped collection called `khokho` which should have max 3 documents.
> db.createCollection("khokho",{capped:true,size:10000,max:3})
  Try inserting more than 3 and see what happens?
  > db.khokho.insertMany(players) 
- check whether a collection is capped or not?
> db.khokho.isCapped()
- drop all documents from `football` collection.
> db.football.remove({})
- delete cricket collection completely.
> db.cricket.drop()
- delete sports database.
> db.dropDatabase() 
- check which database you are connected to ?
>  db
- connect to test database
> use test


```js
var players = [
  {
    name: "player 1",
    email: "p1gmail.com",
    age:21,
    bid_price:"$20K"
  },
  {
    name: "player 2",
    email: "p2gmail.com",
    age:22,
    bid_price:"$25K"
  },
  {
    name: "player 3",
    email: "p1gmail.com",
    age:23,
    bid_price:"$22K"
  },
  {
    name: "player 4",
    email: "p1gmail.com",
    age:20,
    bid_price:"$20K"
  }
]
```
