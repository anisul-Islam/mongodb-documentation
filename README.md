- run the mongoshell: `mongo + enter`
- database
  - show all the databases: `show dbs`
  - create and switch to database: `use databaseName`
  - check which database you are in: `db + Enter`
  - delete database: `db.dropDatabase()`
- collection / table
  - create collection: `db.createCollection(name, options)`
  - show collections: `show collections`
  - To create a collection (table) and add document (row) we can use insert or save method:
    `db.collectionName.insert([{document1},{document2}])`
    `db.collectionName.insertOne({document1})`
    `db.collectionName.insertMany([{document1},{document2}])`
  - drop a collection: db.collectionName.drop()

<br>

- CRUD = Create, Read, Update, Delete

- Create data- inserting data to user collection example

  ```js
    {
      name : "anisul islam",
      age : 31,
      languages: ["bangla", "english"]
     }

  // insertOne()
   db.users.insertOne({name : "anisul islam",age : 31,languages: ["bangla", "english"]})

  // insertMany()
   db.users.insertMany([{name : "rima islam",age : 31,languages: ["urdu", "bangla"]}, {name : "rabeya begum",age : 31,languages: ["hindi", "bangla"]}])

  ```

- Read / Find data

  - read data syntax: `db.collectionName.find()`
  - read data in an easy way syntax: `db.collectionName.find().pretty()`
  - read a specific data syntax: `db.collectionName.find({field: fieldValue})`
    - example: `db.users.find({name: "anisul islam"})`
  - limit data syntax: `db.collectionName.find({field: fieldValue}).limit(NumberOfRows)`
    - example: `db.users.find({age: 31}).limit(2)`

- Update Data

  - update data syntax: `db.collectionName.update(selection_item, update_data)`
  - update data syntax: `db.collectionName.updateOne(selection_item, update_data)`
  - update data syntax: `db.collectionName.updateMany(selection_item, update_data)`
  - find one and update data syntax: `db.collectionName.findOneAndUpdate(selection_item, update_data)`
  - example: `db.users.update({name:"anisul islam"},{$set:{age:32}})`

- Delete data

  - delete data syntax: `db.collectionName.deleteOne(selection)
    - example: `db.users.deleteOne({name:"anisul islam"})`
  - delete data syntax: `db.collectionName.deleteOne()
  - delete many data syntax: `db.collectionName.deleteMany({selected_item})
  - delete many data syntax: `db.collectionName.deleteMany({})

- learn how to use mongodb compass: try CRUD operation there

- how to use mongodb in VSCode

  - use mongoose
  - connect mongodb with the help of mongoose

- sorting: -1 is used for descending, 1 is for ascending
  - syntax: `db.collecttionName.find().sort({fieldName:-1/1})`
