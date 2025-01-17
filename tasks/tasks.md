# Tasks

## Task 1

### Description

- Setup SGW using setup 1
- Use Postman to check if SGW is working (use Admin PORT)

### Observations
couldnt do it because config2 has admin interface and config1 which belongs tp setup1 doesnt have admin interface.



## Task 2

### Description

- Setup SGW using setup 2
- Create a Database using Postman
- Create a Document using Postman
- Get the document using Postman

### Observations
creating a database using postman


created a document using postman

{
    "id": "2",
    "ok": true,
    "rev": "1-622c50a7af0ecb76dff71baa74d13333"
}
created a doc using postman

{
    "_id": "1",
    "_rev": "1-8a4f0130acffc27a65a4137f1051bed5",
    "name": "Ramya",
    "task": "2"
}

## Task 3

### Description

- This task continues from the previous task
- Create a dummy document from CB UI
- Get the document contents using Postman
- Delete the document using Postman

### Observations


## Task 4

### Description

- Create a document from Couchbase Server UI
- Review the revision IDs and explain the different values in revision IDs

### Observations

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
