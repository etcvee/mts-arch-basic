```
test> use college
switched to db college

college> for (var i = 1; i <= 100000; ++i) { db.authors.insertOne({ "_id": "" + i,  "birth_date": "01.01.2023", "birth_year": "2023", "title": "Author " + i, "email": "Author" + i + "@email.com", "first_name": "FirstName" + i, "last_name": "LastName" + i }); }
{ acknowledged: true, insertedId: '100000' }

college> for (var i = 1; i <= 100000; ++i) { db.presentations.insertOne({ "_id": "" + i, "title": "Presentation Title " + i, "author_id": "" + i, "date": "01.01.2023"   }) }
{ acknowledged: true, insertedId: '100000' }
```