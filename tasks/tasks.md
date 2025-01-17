# Tasks

## Task 1

### Description

- Setup SGW using setup 1
- Use Postman to check if SGW is working (use Admin PORT)

### Observations

It says "ADMIN": true in the response

## Task 2

### Description

- Setup SGW using setup 2
- Create a Database using Postman
- Create a Document using Postman
- Get the document using Postman

### Observations

Got a 201 in create Database and no output
Got an array of available database in Get database 
<img width="894" alt="Screenshot 2025-01-17 at 2 36 28 PM" src="https://github.com/user-attachments/assets/c395f4a9-6f2a-47fe-a9d9-7f7755789358" />

Got this in create a document : 
{
    "id": "1",
    "ok": true,
    "rev": "1-622c50a7af0ecb76dff71baa74d13333"
}
Got this in get document : 
{
    "_id": "1",
    "_rev": "1-622c50a7af0ecb76dff71baa74d13333",
    "key1": "value1",
    "key2": "value2"
}

## Task 3

### Description

- This task continues from the previous task
- Create a dummy document from CB UI
- Get the document contents using Postman
- Delete the document using Postman

### Observations

Updated the Database, and then did get document and recieved the contents 

## Task 4

### Description

- Create a document from Couchbase Server UI
- Review the revision IDs and explain the different values in revision IDs

### Observations

The _sync rev is the revision id by Sync Gateway when the document is updated in SGW that too only when shared bucket access is true

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

For

1. enable_shared_bucket_access: false, import_docs: false
new documents created on cb_ui , you cant get the document through postman as document not updated in sync gateway, but the updation of the document is visible through postman

For 

3. enable_shared_bucket_access: true, import_docs: false
{
    "error": "Bad Request",
    "reason": "1 errors:\nInvalid configuration - import_docs enabled, but enable_shared_bucket_access not enabled"
}
