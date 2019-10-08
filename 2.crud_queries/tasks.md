1. Create a database named `blog`.

use blog

2. Create a collection called 'articles'.

db.createCollection('articles')

3. Insert multiple documents(at least 3) into articles. It should have fields

db.articles.insertMany([{title: 'GOT-1', description: 'A', author: {name: 'A', age: 65}, tags: ['A']},
{title: 'GOT-2', description: 'B', author: {name: 'B',  age: 66}, tags: ['B']},
 {title: 'GOT-3', description: 'C', author: {name: 'C', age: 67}, tags: ['C']}])

4. Find all the articles using `db.COLLECTION_NAME.find()`

db.articles.find()

5. Find a document using _id field.

db.articles.find({ "_id" : ObjectId("5d9cb039b43283ca02645914")})


6. Find documents using title and author's name field.

db.articles.find({title: 'GOT-1'})
db.articles.find({title: 'GOT-2'})
db.articles.find({title: 'GOT-3'})

7. Find document using a specific tag.

db.articles.find({'author.name': 'A'})
db.articles.find({tags: 'B'})

8. Update title of a document using its _id field.

db.articles.update({_id: ObjectId("5d5c280962da9e9b5f997eb0")}, {$set: {title: 'GOT-1'}})

9. Update a author's name using article's title.

db.articles.update({title: 'C'}, {$set: {'author.name': 'CC'}})

10. rename details field to description from articles collection. 

db.articles.updateMany({}, {$rename: {'details':'description'}})

11. Add additional tag in a specific document.



12. Update an article's tags using $set and without $set.
  - Write the differences here ?

13. Increment an auhtor's age by 5.  

db.articles.update({title: 'GOT-2'}, {$inc: {'author.age': 5}})



14. Delete a document using _id field with `db.COLLECTION_NAME.remove()`.

db.COLLECTION_NAME.remove(). db.articles.remove({_id: ObjectId("5d5c280962da9e9b5f997eb2")})

Use sample.js data for below queries.



1. Find all males who play cricket.

db.users.find({$and: [{sports: {$in: ["cricket"]}}, {gender: {$eq: "Male"}}]})

2. Update user with extra golf field in sports array whose name is "Steve Ortega".

db.users.update({name: {$eq: "Steve Ortega"}}, {$push: {sports: "golf"}})

3. Find all users who play either 'football' or 'cricket'.

db.users.find({sports: {$all : ['football', 'cricket']}})

4. Find all users whose name includes 'ri' in their name.

db.users.find({name: {$regex: /ri/}})
