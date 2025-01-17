# Tasks

## Task 1

### Description

- Setup SGW using setup 1
- Use Postman to check if SGW is working (use Admin PORT)

### Observations
```
```
"api": {
        "admin_interface": "0.0.0.0:4985"
      },
```

```
## Task 2

### Description

- Setup SGW using setup 2
- Create a Database using Postman
- Create a Document using Postman
- Get the document using Postman

### Observations
match the sample bucket
then geT

## Task 3


### Description

- This task continues from the previous task
- Create a dummy document from CB UI
- Get the document contents using Postman
- Delete the document using Postman

### Observations
update database from ui
## Task 4

### Description

- Create a document from Couchbase Server UI
- Review the revision IDs and explain the different values in revision IDs

### Observations
There are different revisions id's because sync gateway processes and if updating it to the new synch value(metadata change)

## Task 5

### Description

- Test the following configurations of SGW database:

```
1. enable_shared_bucket_access: false, import_docs: false
2. enable_shared_bucket_access: false, import_docs: true
3. enable_shared_bucket_access: true, import_docs: false
4. enable_shared_bucket_access: true, import_docs: true
```

### Observations
1) updates with option 1 on server ui do not show on sgw and new documets created wont be found
2) false true did not work - shared bucket access with import docs doesnt make sense
3) this updates one way , changes on sync gateway will reflect in server but not the other way
4) both ways work
