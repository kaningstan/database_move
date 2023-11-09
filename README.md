# database_move
** 01.Create a Database called movies?**
      ``` use movies```


 **02. Create a collection called moviedetails.**
    ```
    db.createCollection("moviedetails")

     moveies> show collections
     moviedetails
     moveies> 
```

**03. Create above 5 movie documents into a moviedetails collection.**
```
      moveies> db.moviedetails.insertMany([{movie_title:"Jurassic Park",type:"adventure",director:"steven spielberg",release_year:1993},{movie_title:"forrest gump",type:"drama",director:"robert zemeckies",release_year:1994},{movie_title:"titanic",type:"romance",director:"james cameron",release_year:1997},{movie_title:"the dark knight",type:"action",director:"christopher nolan",release_year:2008},{movie_title:"avatar",type:"science fiction",diretor:"james cameron",release_year:2009}])


{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId("654c83519226ad1f1466c049"),
    '1': ObjectId("654c83519226ad1f1466c04a"),
    '2': ObjectId("654c83519226ad1f1466c04b"),
    '3': ObjectId("654c83519226ad1f1466c04c"),
    '4': ObjectId("654c83519226ad1f1466c04d")
  }
}
```

04.List all documents created.

     
```
 db.moviedetails.find()
[
  {
    _id: ObjectId("654c83519226ad1f1466c049"),
    movie_title: 'Jurassic Park',
    type: 'adventure',
    director: 'steven spielberg',
    release_year: 1993
  },
  {
    _id: ObjectId("654c83519226ad1f1466c04a"),
    movie_title: 'forrest gump',
    type: 'drama',
    director: 'robert zemeckies',
    release_year: 1994
  },
  {
    _id: ObjectId("654c83519226ad1f1466c04b"),
    movie_title: 'titanic',
    type: 'romance',
    director: 'james cameron',
    release_year: 1997
  },
  {
    _id: ObjectId("654c83519226ad1f1466c04c"),
    movie_title: 'the dark knight',
    type: 'action',
    director: 'christopher nolan',
    release_year: 2008
  },
  {
    _id: ObjectId("654c83519226ad1f1466c04d"),
    movie_title: 'avatar',
    type: 'science fiction',
    diretor: 'james cameron',
    release_year: 2009
  }
]
```

**05List James Cameron’s movies.**

```
db.moviedetails.find({director:"james cameron"})
[
  {
    _id: ObjectId("654c83519226ad1f1466c04b"),
    movie_title: 'titanic',
    type: 'romance',
    director: 'james cameron',
    release_year: 1997
  },
  {
    _id: ObjectId("654c8b3b9226ad1f1466c04e"),
    movie_title: 'avatar',
    type: 'science fiction',
    release_year: 2009,
    director: 'james cameron'
  }
]
```

** 06.List  James Cameron’s movies released in 2009. **
```
  db.moviedetails.find({director:"james cameron",release_year:2009})

  
[
  {
    _id: ObjectId("654c8b3b9226ad1f1466c04e"),
    movie_title: 'avatar',
    type: 'science fiction',
    release_year: 2009,
    director: 'james cameron'
  }
]
```

**07.Delete the movie which you don’t like.**
```
 db.moviedetails.remove({movie_title:"forrest gump"})

```

**08.Add the movie which is your favourite.**
 ```
     db.moviedetails.insertOne({movie_title:"geetha govintham",type:"love drama",director:"parasuram",release_year:2018})


      _id: ObjectId("654c9e869226ad1f1466c04f"),
    movie_title: 'geetha govintham',
    type: 'love drama',
    director: 'parasuram',
    release_year: 2018
  }
```





**09.List movie Directed  by Christopher Nolan in 1994. **

```
  db.moviedetails.find({director:"christopher nolan",release_year:1994})

```


**10.List out the Director’s Name in your document. **
```
    db.moviedetails.distinct("director")

      
  'christopher nolan',
  'james cameron',
  'parasuram',
  'steven spielberg'
```





























