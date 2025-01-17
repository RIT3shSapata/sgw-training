# Tasks

## Task 1

### Description

- Setup SGW using setup 1
- Use Postman to check if SGW is working (use Admin PORT)

### Observations

We expose ports `4984` to `4986`, amongst which port `4985` is the admin port. [Screenshot](/images/task-1.png).
+ We had to correct the host in postman too.
Response:
```json
{"ADMIN":true,"couchdb":"Welcome","vendor":{"name":"Couchbase Sync Gateway","version":"3.2"},"version":"Couchbase Sync Gateway/3.2.1(15;release) EE","persistent_config":true}
```

## Task 2

### Description

- Setup SGW using setup 2
- Create a Database using Postman
- Create a Document using Postman
- Get the document using Postman

### Observations
+ We need to create a bucket named `test` with Flush: `true` and then run the PUT request to create the database, we get response as 201, created.
+ Create document request runs alright: we get a 200 with response
```json
{
    "id": "1",
    "ok": true,
    "rev": "1-622c50a7af0ecb76dff71baa74d13333"
}
```
+ To get the document change the doc id to `1`, we get a 200 with response
```json
{
    "_id": "1",
    "_rev": "1-622c50a7af0ecb76dff71baa74d13333",
    "key1": "value1",
    "key2": "value2"
}
```

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
