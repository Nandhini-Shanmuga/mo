Create a collection called “movies” and perform the queries listed below:
1) Add 5 movies to the collection, every movie document should include the following properties: 
name, genre, rating (out of 10) and language:
Solution1:
db.movies.insertMany([
{
 "name": "Black Panther",
 "language": "ENGLISH",
 "rating": 8.1,
 "type": "Action Adventure Fantasy"
 },
 {
 "name": "Loin King",
 "language": "ENGLISH",
 "rating":9.0,
 "type": "Comady Animation"
 },
 {
 "name": "Toy Story 4",
 "language": "ENGLISH",
 "rating":7.3,
 "type": "Fantasy Adventure"
 },
 {
 "name": "Brightburn",
 "language": "ENGLISH",
 "rating":4.5,
 "type": "Drama Sci-fi"
 },
 {
 "name": "Hellboy",
 "language": "ENGLISH",
 "rating":5.3,
 "type": "Supernatural Fantasy"
 }
])
2) Write a query that returns all the movies
Solution2: db.movies.find().pretty()
3) Write a query to find anyone movie name using findOne method (Do not use limit() method)
Solution3: db.movies.findOne({})Create a collection called “movies” and perform the queries listed below:
1) Add 5 movies to the collection, every movie document should include the following properties: 
name, genre, rating (out of 10) and language:
Solution1:
db.movies.insertMany([
{
 "name": "Black Panther",
 "language": "ENGLISH",
 "rating": 8.1,
 "type": "Action Adventure Fantasy"
 },
 {
 "name": "Loin King",
 "language": "ENGLISH",
 "rating":9.0,
 "type": "Comady Animation"
 },
 {
 "name": "Toy Story 4",
 "language": "ENGLISH",
 "rating":7.3,
 "type": "Fantasy Adventure"
 },
 {
 "name": "Brightburn",
 "language": "ENGLISH",
 "rating":4.5,
 "type": "Drama Sci-fi"
 },
 {
 "name": "Hellboy",
 "language": "ENGLISH",
 "rating":5.3,
 "type": "Supernatural Fantasy"
 }
])

2) Write a query that returns all the movies
Solution2: db.movies.find().pretty()

3) Write a query to find anyone movie name using findOne method (Do not use limit() method)

Solution3: db.movies.findOne({})

4) Write a query that returns the three highest rated movies
Solution4: db.movies.find({}).sort({rating:-1}).limit(3)
5) Add a key called achievements in any two documents. One document should have ‘Super hit’ and 
other should have ‘Super Duper Hit’ as value to key achievements. This task should be performed 
in two ways-
• Using update() method 
• Using save() method
Hint: For save, you have to query the object and store it in a variable first
 Solution5:
db.movies.update(
 { 'name': 'Brightburn' },
 {
 $set: {
 "name": "Brightburn",
 "language": "ENGLISH",
 "rating":5.3,
 "type": "Supernatural Fantasy",
 "achievements":"Super hit"
 }
 }
)
var a = db.movies.find({ "name": "Loin King"})
db.movies.update(
 { 'name': 'Loin King' },
 {
 $set: {
 "name": "Loin King",
 "language": "ENGLISH",
 "rating":5.3,
 "type": "Supernatural Fantasy",
 "achievements":"Super duper hit"
 }
 }
)

6) Write a query that returns all the movies that have both the ‘Super hit’ and the ‘Super Duper hit’’ 
achievements
Solution6:
db.movies.find({$and : [{"achievements":"Super duper
hit"},{"achievements":"Super hit"}]})

7) Write a query that returns only those movies that have achievements
Solution7:
db.movies.find({$or : [{"achievements":"Super duper 
hit"},{"achievements":"Super hit"}]})
