# Tasks

## Task 1

### Description

- Setup SGW using setup 1
- Use Postman to check if SGW is working (use Admin PORT)

### Observations

- The admin does not work when accessed from an external environment because of the nature of design of sync gateway and security purposes.
- It works when an API key value is added to config1.json and admin_interface value is given as 0.0.0.0:4985 allowing any IP address to access to admin port.

## Task 2

### Description

- Setup SGW using setup 2
- Create a Database using Postman
- Create a Document using Postman
- Get the document using Postman

### Observations

- I did not add the index service to the initial cb nodes. So i had to restart one of them and add the index service to the cluster 
- I was able to create db1(database) and then I was able to create a document and retrieve it using Postman

## Task 3

### Description

- This task continues from the previous task
- Create a dummy document from CB UI
- Get the document contents using Postman
- Delete the document using Postman

### Observations

- I was able to add the document to sync_gateway bucket 
- I had to use Postman to update my database(db1) first.
- And after it updated, I was able to retrieve my document using its Id(2).
- I also had to change the name of the bucket in the body of the request for Update database in Postman

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
