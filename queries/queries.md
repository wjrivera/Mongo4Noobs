# Queries

1. [Find Stuff](#find_stuff)
2. [Filter Data](#filter_data)

Database:       `database`
<br>
Collection:     `collection`

#### Sample Document

```
db.collection.insert(
{
    "_id": 25,
    "Name": "Michael",
    "Address": {
        "Street": "123 Main Street",
        "Zip": 12345
    },
    
    "Alias": ["Mike", "Miguel", "Mickey"],
    "Working": true,
    "DOB": ISODate("1999-01-01T12:30:00Z")
});    
```

### <a id="find_stuff"></a>Find Stuff
Get all documents
> `db.collection.find({})`

Get all documents and make them look pretty
> `db.collection.find({}).pretty()`

Get count of all documents
> `db.collection.find({}).count()`

Find all the documents that have a field name `Name` with a value of `Michael`
> `db.collection.find({"Name": "Michael"})`

Find all the documents that have a field name `Alias` with a value of `Miguel`
> `db.collection.find({"Alias": "Miguel"})`

Find all the documents that have a field name `Address.Street` with a value of `123 Main Street` (Nested document)
> `db.collection.find({"Address.Street": "123 Main Street"})`

Get all users with `DOB` less than `12/30/2004`
> `db.collection.find({"DOB": { "$lt": ISODate("2004-12-31")}})`

Find how many `Michael` are on the collection
> `db.collection.find({"Name": "Michael"}).count()`

Find the first document that has a field name `Name` with a value of `Michael`
> `db.collection.find({"Name": "Michael"}).limit(1)`

### <a id="filter_data"></a>Filter Data
Find a field name `Name` that has a value of `Michael` and display only the `Address`
> `db.collection.find({"Name": "Michael"}, {"_id": 0, "Address": 1})`

