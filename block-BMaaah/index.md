writeCode

Write code to execute below expressions.

1. Create a database named `blog`.
```js
use blog
```
2. Create a collection called 'articles'.
```js
db.createCollection('articles')
```
3. Insert multiple documents(at least 3) into articles. It should have fields

- title as string
- createdAt as date
- details as String
- author as nested object
  - author should have
    - name
    - email
    - age
    - example author: {name: 'abc', email: 'abc@gmail', age: 25}
- tags : Array of strings like ['html', 'css']
```js


db.blog.insertMany([
  {
  title: "author1",
  createdAt:12/03/1985,
  details:"pmfpmpmf opmoknf pompmefnv",
  author:{
    name:'author1',
    email: 'author1@gmail',
    age: 25
  },
  tags:['html', 'css']
},
{
  title: "author2",
  createdAt:12/03/1986,
  details:"pmfpmpmf opmoknf pompmefnv",
  author:{
    name:'author2',
    email: 'author2@gmail',
    age: 25
  },
  tags:['java', 'python']
},
{
  title: "author3",
  createdAt:12/03/1987,
  details:"pmfpmpmf opmoknf pompmefnv",
  author:{
    name:'author3',
    email: 'author3@gmail',
    age: 25
  },
  tags:['js', 'mongo']
}
])
// An article should look like in the database
{
  _id: 'some_random_id',
  title: '',
  details: '',
  author: {
    name: '',
    email: '',
    age: ''
  },
  tags: ['js', 'mongo']
}
```

4. Find all the articles using `db.COLLECTION_NAME.find()`
```js
db.blog.find().pretty()
```
5. Find a document using \_id field.
```js
db.blog.findOne({"_id" : ObjectId("627a50b9d58ed43712f1224f")})
```
6. 1. Find documents using title
```js
db.blog.find({title : "author3"})
```
7. 2. Find documents using author's name field.
```js
db.blog.find({'author.name' : 'author3'})
```
8. Find document using a specific tag.
```js
db.blog.find({tags : 'java'})
```
9. Update title of a document using its \_id field.
```js
db.blog.update({ _id : ObjectId("627a50b9d58ed43712f1224f")}, {$set: {title: "author first"}})
```
10. Update a author's name using article's title.
```js
db.blog.update({title : "author2"}, {$set: {'author.name': 'author second'}})
```
11. rename details field to description from all articles in articles collection.
```js
db.blog.updateMany({},{ $rename: { "details": "description"}})
```
12. Add additional tag in a specific document.
```js
db.blog.update({title: "author3"}, {$push: {tags: "html"}})
```
13. Update an article's title using $set and without $set.
```js

```
- Write the differences here ?
```js
```
13. find an article using title and increment it's auhtor's age by 5.
```js
db.blog.update({title: "author3"}, {$set: {age: 30}})
```
14. Delete a document using \_id field with `db.COLLECTION_NAME.remove()`.
```js
db.blog.remove({_id : ObjectId("627a50b9d58ed43712f12251")})

```

// Sample data

```js
db.users.insertMany([
  {
    age: 49,
    name: "Maurice Brock",
    email: "wuk@hibpiz.ch",
    gender: "Female",
    sports: ["cricket", "football"],
    scores: [24, 35, 18, 16],
    weight: 45,
  },
  {
    age: 37,
    birthday: "7/15/1986",
    name: "Virgie Cunningham",
    email: "ezogafa@de.gm",
    gender: "Male",
    sports: ["football"],
    scores: [17, 35, 43],
    weight: 52,
  },
  {
    age: 48,
    birthday: "5/14/1961",
    name: "Alexander Holt",
    email: "han@mu.pe",
    gender: "Male",
    sports: ["cricket", "football", "TT"],
    scores: [24, 30, 16],
    weight: 55,
  },
  {
    age: 53,
    birthday: "11/15/1963",
    name: "Derek Dawson",
    email: "polril@now.de",
    gender: "Male",
    sports: ["cricket", "hockey"],
    scores: [20, 15, 38, 23],
    weight: 49,
  },
  {
    age: 34,
    birthday: "7/24/1964",
    name: "Cynthia Cobb",
    email: "wujjarpob@jecimpar.gu",
    gender: "Female",
    sports: ["cricket"],
    scores: [41, 17, 28],
    weight: 51,
  },
  {
    age: 33,
    birthday: "10/26/1982",
    name: "Isabella Atkins",
    email: "ononuzas@givhoz.ca",
    gender: "Female",
    sports: ["cricket", "football", "hockey", "TT"],
    scores: [14, 38, 29, 45, 20],
    weight: 49,
  },
  {
    age: 47,
    birthday: "10/12/1978",
    name: "Katharine Bryan",
    email: "zo@pebi.sa",
    gender: "Male",
    sports: ["TT", "hockey", "khokho"],
    scores: [27, 20, 34],
    weight: 58,
  },
  {
    age: 41,
    birthday: "1/28/1991",
    name: "Beatrice Fleming",
    email: "ufufsa@pujizren.tk",
    gender: "Female",
    sports: ["football", "khokho"],
    scores: [30, 20, 15, 29, 43],
    weight: 47,
  },
  {
    age: 26,
    birthday: "3/23/1998",
    name: "Tom Fields",
    email: "wasodjow@ofaba.gf",
    gender: "Female",
    sports: ["khokho"],
    scores: [37, 29, 18, 43, 49],
    weight: 50,
  },
  {
    age: 33,
    birthday: "11/14/1960",
    name: "Steve Ortega",
    email: "dupus@ca.ls",
    gender: "Female",
    sports: ["cricket", "football", "hockey"],
    scores: [12, 15, 20],
    weight: 51,
  },
  {
    age: 24,
    birthday: "1/5/1994",
    name: "Suraj Kumar",
    weight: 50,
    gender: "Male",
    sports: ["football", "cricket", "TT"],
  },
]);
```

Insert above data into database to perform below queries:-

- Find all males who play cricket.
```js
db.users.find({gender: {$ne: "Female"}})
```
- Update user with extra golf field in sports array whose name is "Steve Ortega".
```js
db.users.update({name: "Steve Ortega"}, {$push: {sports: "golf"}})
```
- Find all users who play either 'football' or 'cricket'.
```js
db.users.find({$or: [{sports: 'football'}, {sports: 'football'}]})

```
- Find all users whose name includes 'ri' in their name.
```js
db.users.find({name: {$all: 'ri'}})
```
