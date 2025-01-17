 # Task 1

- had to edit basic auth to get the following 
```
{
    "ADMIN": true,
    "couchdb": "Welcome",
    "vendor": {
        "name": "Couchbase Sync Gateway",
        "version": "3.2"
    },
    "version": "Couchbase Sync Gateway/3.2.1(15;release) EE",
    "persistent_config": true
}

```
# Task 2
- Got 201 after creating bucket
> Assumed it would create a bucket on its own 


# Task 3

Created 
```
{
  "click": "samridh",
  "with JSON": "created"
}
```
Upon getting docs
```
{
    "_id": "1234",
    "_rev": "1-5c86b2dfa5130182672c81ae5455ad14",
    "click": "samridh",
    "with JSON": "created"
}
```
> Had to change ID in url 
Dropping it

- COuld not delete, say conflict error
- tried to create a docs viapostman and delete the doc and worked 
> due to shared bucket ig?
