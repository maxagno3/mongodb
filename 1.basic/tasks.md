#### write commands for following mongodb opertaions

1. create a database named `sports`
// Answer here ..
//use sports

2. list all databases present in local mongod server.
// Answer here..
//show dbs

3. create 3 collections named `cricket`, `football`, `TT` in sports database.

//db.createCollection('cricket')
db.createCollection('football')
db.createCollection('TT')

4. add 3 players in each of above collections which should have fields like `name`, `age`, `email`, state and auction_price.

//db.cricket.insert({name : 'Max', age: 20, email: 'abc@xyz.com', auction_price: 20})
db.football.insert({name : 'Rex', age: 22, email: 'abd@xyz.com', auction_price: 10})
db.TT.insert({name : 'Tix', age: 18, email: 'wbc@xyz.com', auction_price: 12})

5. list all collections in sports database.

//db.getCollectionNames()

6. rename `TT` collection to `tennis`.

//db.TT.renameCollection('tennis')

7. create a capped collection called `khokho` which should have max 3 documents.
  Try inserting more than 3 and output the result here ?

//db.createCollection('khokho', {capped: true, size: 64 * 1024, max: 3})
db.khokho.insert({name: 'Hyun', age: 30})
db.khokho.insert({name: 'Ying', age: 35})
db.khokho.insert({name: 'Cyrus', age: 20})
db.khokho.insert({name: 'Gomez', age: 24})
db.khokho.find()

//Output
//{ "_id" : ObjectId("5ea6ac52b48b10dbaaff6849"), "name" : "Ying", "age" : 35 }
{ "_id" : ObjectId("5ea6ac59b48b10dbaaff684a"), "name" : "Cyrus", "age" : 20 }
{ "_id" : ObjectId("5ea6ac5fb48b10dbaaff684b"), "name" : "Gomez", "age" : 24 }

8. check whether a collection is capped or not?

//db.cricket.isCapped()

9. remove all documents from `football` collection.

//db.football.remove({})

10. delete cricket collection completely.

//db.cricket.drop()

11. rename database sports to games

//db.copyDatabase('sports', 'games', 'localhost')
use sports
db.dropDatabase()

12. delete sports database. 
