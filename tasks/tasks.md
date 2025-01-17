# Tasks

## Task 1

### Description

- Setup SGW using setup 1
- Use Postman to check if SGW is working (use Admin PORT)

### Observations
-The SGW was setup using the Setup 1.
-curl localhost:4984 sends a reply 
-Managed to curl into the bucket
-Got socket hang up error
-4984 works, 4985 doesn't work
- Added
  {
  "api": {
    "admin_interface": "0.0.0.0:4985"
  },
  To the config1.json file to fix the issue.
-SGW working sends a request
Authorization: Basic QWRtaW46MTIzNDU2Nzg=
User-Agent: PostmanRuntime/7.43.0
Accept: */*
Cache-Control: no-cache
Postman-Token: 1a44cbd3-7fde-4882-9ddc-b2e6079d4b90
Host: 127.0.0.1:4985
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

## Task 2

### Description

- Setup SGW using setup 2
- Create a Database using Postman
- Create a Document using Postman
- Get the document using Postman

### Observations
- Created SGW using setup 2
  
- Successfully created a Database in the bucket SampleBucket (creatd 5 documents inside it)
  
- Created a document
  {
    "id": "1",
    "ok": true,
    "rev": "1-622c50a7af0ecb76dff71baa74d13333"
  }

-Got the document using Postman
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
- Created the dummy document
  {
    "desc": "this is a dummy document"
  }
- Updated the db using Update Database
- Got the dummy document using Get Document
  {
    "_id": "dummy",
    "_rev": "1-e43ed042c193383b45db89c0ea2ae61b",
    "desc": "this is a dummy document"
  }
- DELETE doesn't work: conflict
  
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
