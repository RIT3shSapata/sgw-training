# Tasks

## Task 1

### Description

- Setup SGW using setup 1
- Use Postman to check if SGW is working (use Admin PORT)

### Observations

- Postman GET url: http://localhost:4984
- Message: "couchdb": "Welcome", vendor: { "name" : "Couchbase Sync Gateway", "version": 3.2} "version": "Couchbase Sync Gateway/3.2.1(15;release) EE",
- Docker commands: docker run -d --name cb_0 -p 8091:8091 couchbase:latest, docker run -d --name sgw -p 4984-4986:4984-4986 -v ./config1.json:/etc/sync_gateway/config.json couchbase/sync-gateway:enterprise

## Task 2

### Description

- Setup SGW using setup 2
- Create a Database using Postman
- Create a Document using Postman
- Get the document using Postman

### Observations

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
