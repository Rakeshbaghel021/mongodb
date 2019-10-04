1. Create a database named `blog`.

use blog

2. Create a collection called 'articles'.

db.createCollection('articles')

3. Insert multiple documents(at least 3) into articles. It should have fields

db.articles.insertMany([{title: 'Abc', description: 'A', author: {name: 'A', email: 'A', age: 65}, tags: ['A']},
{title: 'Bca', description: 'B', author: {name: 'B', email: 'B', age: 66}, tags: ['B']},
 {title: 'Cab', description: 'C', author: {name: 'C', email: 'C', age: 67}, tags: ['C']}])

4. Find all the articles using `db.COLLECTION_NAME.find()`

db.articles.find()

5. Find a document using _id field.

db.articles.find({_id: ObjectId("5d5c280962da9e9b5f997eb0")})

6. Find documents using title and author's name field.

db.articles.find({title: 'Abc'})

7. Find document using a specific tag.

db.articles.find({'author.name': 'A'})
db.articles.find({tags: 'B'})

8. Update title of a document using its _id field.

db.articles.update({_id: ObjectId("5d5c280962da9e9b5f997eb0")}, {$set: {title: 'Abc'}})

9. Update a author's name using article's title.

db.articles.update({title: 'C'}, {$set: {'author.name': 'CC'}})

10. rename details field to description from articles collection. 

11. Add additional tag in a specific document.

12. Update an article's tags using $set and without $set.
  - Write the differences here ?

13. Increment an auhtor's age by 5.  

14. Delete a document using _id field with `db.COLLECTION_NAME.remove()`.

Use sample.js data for below queries.

1. Find all males who play cricket.

2. Update user with extra golf field in sports array whose name is "Steve Ortega".

3. Find all users who play either 'football' or 'cricket'.

4. Find all users whose name includes 'ri' in their name.
