# Database
**MongoDB Exercise 01**
**1. Create a Database called movies.**
```  use movies  ```
**2. Create a collection called moviedetails.**
``` movies> db.createCollection("moviedetails")
{ ok: 1 }
movies>   ``` 
**3. Create above 5 movie documents into a moviedetails collection.**
``` movies> db.moviedetails.insertMany([{"Movie-Title": "Forrest Gump" , "Genre/Type": "Drama" , "Director": "Robert Zemeckies" ,"Release Year":"1994",},{"Movie-Title": "Titanic" , "Genre/Type": "Romance" , "Director": "James Cameron" ,"Release Year":"1997",},{"Movie-Title": "The Dark Knight" , "Genre/Type": "Action" , "Director": "Christopher Nolan" ,"Release Year":"2008",},{"Movie-Title": "Jurassic Park" , "Genre/Type": "Science Fiction" , "Director": "James Cameron" ,"Release Year":"2009",}])
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId("654c9967daa386c5ab5f7d22"),
    '1': ObjectId("654c9967daa386c5ab5f7d23"),
    '2': ObjectId("654c9967daa386c5ab5f7d24"),
    '3': ObjectId("654c9967daa386c5ab5f7d25")
  }
}
movies>```
**4. List all documents created.**
```movies> db.moviedetails.find()
[
  {
    _id: ObjectId("654c8a1bdaa386c5ab5f7d11"),
    'Movie-Title': 'Jurassic Park',
    'Genre/Type': 'Adventure',
    Director: 'Steven Spielberg',
    'Release Year': '1993'
  },
  {
    _id: ObjectId("654c8b76daa386c5ab5f7d12"),
    'Movie-Title': 'Forrest Gump',
    'Genre/Type': 'Drama',
    Director: 'Robert Zemeckies',
    'Release Year': '1994'
  },
  {
    _id: ObjectId("654c8bbedaa386c5ab5f7d13"),
    'Movie-Title': 'Titanic',
    'Genre/Type': 'Romance',
    Director: 'James Cameron',
    'Release Year': '1997'
  },
  {
    _id: ObjectId("654c8bdfdaa386c5ab5f7d14"),
    'Movie-Title': 'The Dark Knight',
    'Genre/Type': 'Action',
    Director: 'Christopher Nolan',
    'Release Year': '2008'
  },
  {
    _id: ObjectId("654c8bffdaa386c5ab5f7d15"),
    'Movie-Title': 'Jurassic Park',
    'Genre/Type': 'Science Fiction',
    Director: 'James Cameron',
    'Release Year': '2009'
  }
]
movies> ```
**5. List James Cameron’s movies.**
``` movies> db.moviedetails.findOne({ "Director": "James Cameron" })
{
  _id: ObjectId("654c9967daa386c5ab5f7d23"),
  'Movie-Title': 'Titanic',
  'Genre/Type': 'Romance',
  Director: 'James Cameron',
  'Release Year': '1997'
}
movies>```
**6. List  James Cameron’s movies released in 2009.**
``` movies> db.moviedetails.findOne({ "Release Year": "2009" })
{
  _id: ObjectId("654c9967daa386c5ab5f7d25"),
  'Movie-Title': 'Jurassic Park',
  'Genre/Type': 'Science Fiction',
  Director: 'James Cameron',
  'Release Year': '2009'
}
movies> ```
**7. Delete the movie which you don’t like.**
``` movies> db.collection_name.insertOne({"Movie-Title": "Leo" , "Genre/Type": "Action" , "Director": "Logesh Kanagaraj" ,"Release Year":"2023",})
{
  acknowledged: true,
  insertedId: ObjectId("654c9ea1daa386c5ab5f7d26")
}
movies>```
**8. Add the movie which is your favourite.**
``` ```
**9. List movie Directed  by Christopher Nolan in 1994.**
```movies> db.moviedetails.find({ "Director": "Christopher Nolan", "Release Year": "1994" })

movies> ```
  **10. List out the Director’s Name in your document.**
``` movies> db.moviedetails.distinct("Director")
[ 'Christopher Nolan', 'James Cameron', 'Robert Zemeckies' ]
movies> ```
