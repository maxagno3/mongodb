1. Create a database named `blog`.

//use blog

2. Create a collection called 'articles'.

//db.createCollection('articles')

3. Insert multiple documents(at least 3) into articles. It should have fields

//db.articles.insert({name: 'Mayank'})
db.articles({name: 'Sagar'})
db.articles({name: 'Sanjib})

4. Find all the articles using `db.COLLECTION_NAME.find()`

//db.articles.find()

5. Find a document using _id field.

//db.articles.find({_id: ObjectId("5ea6c4af2f42667724aaa92a")})

6. Find documents using title and author's name field.

//db.articles.update({_id: ObjectId("5ea6c31b2f42667724aaa929")}, {title: 'ITHALS', author: 'R. Singh', age: 40})
db.articles.update({_id: ObjectId("5ea6c4c32f42667724aaa92b")}, {title: '2 States', author: 'C. Bhagat', age: 45})
db.articles.update({_id: ObjectId("5ea6c4d02f42667724aaa92c")}, {title: 'Goosenumps', author: 'R.L Stine', age: 50})
//db.articles.find({},{title: 1, author: 1})

7. Find document using a specific tag.

//db.articles.find({age: 45})

8. Update title of a document using its _id field.

//db.articles.update({_id: ObjectId("5ea6c4c32f42667724aaa92b")}, {$set: {title: '2 States'}}

9. Update a author's name using article's title.

//db.articles.update({_id: ObjectId("5ea6c4c32f42667724aaa92b")}, {$set: {author: 'Chetan'}})

10. rename details field to description from articles collection. 

//db.articles.update({_id: ObjectId("5ea6c4c32f42667724aaa92b")}, {$set: {details: 'Beautiful Book'}})
db.articles.update({_id: ObjectId("5ea6c4c32f42667724aaa92b")}, {$rename: {details: 'description'}})

11. Add additional tag in a specific document.

//db.articles.update({_id: ObjectId("5ea6c4c32f42667724aaa92b")}, {$set: {gender: 'Male'}})

12. Update an article's tags using $set and without $set.
  - Write the differences here ?

//db.articles.update({_id: ObjectId("5ea6c4c32f42667724aaa92b")}, {$rename: {gender: 'Gender'}})
db.articles.update({_id: ObjectId("5ea6c4c32f42667724aaa92b")}, {$set: {Sold: 'Above 10,000'}})

13. Increment an auhtor's age by 5.

//db.articles.update({_id: ObjectId("5ea6c4c32f42667724aaa92b")}, {$inc: {age: 10}})

14. Delete a document using _id field with `db.COLLECTION_NAME.remove()`.

//db.articles.remove({_id: ObjectId("5ea6c31b2f42667724aaa929")})

Use sample.js data for below queries.

1. Find all males who play cricket.

db.users.find({gender: 'male'} && {sports: 'cricket'})

2. Update user with extra golf field in sports array whose name is "Steve Ortega".

//db.users.update({name: 'Steve Ortega'} , {$push: {sports: 'golf'}})

3. Find all users who play either 'football' or 'cricket'.

//db.users.find({sports: 'football' || 'cricket'})

4. Find all users whose name includes 'ri' in their name.

//db.users.find({name: /\w*ri\w*/ig})