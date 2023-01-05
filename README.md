# mongo-course

## Class 02

### Docker Commands

#### Up Mongo

```sh
docker-compose up -d mongodb
```

#### Check Mongo

```sh
docker-compose ps
```

## Class 03

### Docker

#### Connect to docker container

```sh
docker-compose exec mongodb bash
```

#### Connect to mongoSH

```sh
mongosh "URI"
```

### MongoSH

#### Some Commands into mongosh

```sh
show dbs
show collection
use("platzi_store")
db.products.find()
```

## Class 04

### - INSERT

> Since an error occurs with the insertion of an object using `insertMany()` funtion, objects after it are not created. — Mongo Course

> We can solve this error sending a seccond param -> `insertMany([{obj1},{obj2}],{ordered:false})`

### - UPDATE

#### Operators (change)

`$set` > add an atribute and update a atribute

`$inc` > increment numbers atributtes

`ObjectId()`

`$rename` > rename a atribute

`$unSet` > remove a atribute

`$push` > push to Arrays

`$pull` > delete to Array

`$in` > Internal operator

`$pop` > delete first (-1) or last (1) value

### - UPDATE - INSERT (upsert)

```js
db.iot.updateOne(
  {
    sensor: "A001",
    date: "2022-01-03",
  },
  {
    $push: {
      readings: 2424,
    },
  },
  {
    upsert: true,
  }
);
```

### DELETE

```js
db.products.deleteOne({ _id: 1 });
db.products.deleteMany({ price: 100 });
db.products.drop();
```
