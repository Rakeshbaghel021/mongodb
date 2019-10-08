#### write commands for following mongodb opertaions

1. create a database named `sports`

use sports

2. list all databases present in local mongod server.

show dbs

3. create 3 collections named `cricket`, `football`, `TT` in sports database.

db.createCollection('cricket') 
db.createCollection('football') 
db.createCollection('TT')

4. add 3 players in each of above collections which should have fields like `name`, `age`, `email`, state and auction_price.

db.cricket.insertMany([{name: 'rakesh', age: 25, email: 'rkrkumar021@gmail.com', state: 'UP', auction_price: 10000}, {name: 'avinash', age: 24, email: 'avi@xyz.com', state: 'orissa', auction_price: 60}, {name: 'chadu', age: 22, email: 'chadu@xyz.com', state: 'AP', auction_price: 60}])

db.football.insertMany([{name: 'vikas', age: 25, email: 'rkrk@gmail.com', state: 'UP', auction_price: 10000}, {name: 'avi', age: 24, email: 'avi@xyz.com', state: 'orissa', auction_price: 60}, {name: 'chaduwala', age: 22, email: 'chadu@xyz.com', state: 'AP', auction_price: 60}])

db.TT.insertMany([{name: 'ishav', age: 25, email: 'ishav@gmail.com', state: 'HP', auction_price: 10000}, {name: 'chadni', age: 24, email: 'achad@xyz.com', state: 'mumbai', auction_price: 60}, {name: 'suraj', age: 22, email: 'suraj@xyz.com', state: 'Bihar', auction_price: 7656}])


5. list all collections in sports database.

show collections

6. rename `TT` collection to `tennis`.

db.TT.renameCollection('tennis')

7. create a capped collection called `khokho` which should have max 3 documents.
  Try inserting more than 3 and output the result here ?

  db.createCollection('khokho', {capped: true, size: 2048, max: 3})

8. check whether a collection is capped or not?

db.khokho.isCapped()

9. remove all documents from `football` collection.

db.football.remove({})

10. delete cricket collection completely.

db.cricket.drop()

11. rename database sports to games

db.copyDatabase('sports', 'games')  

12. delete sports database. 

use sports
db.dropDatabase()
