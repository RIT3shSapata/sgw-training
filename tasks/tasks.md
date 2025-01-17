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
+ To create a document using UI that is understandable to SGW we need to add proper body, copied it from doc: 1
```json
{
  "key1": "valuefrom-ui",
  "key2": "value2from-ui",
  "_sync": {
    "rev": "1-622c50a7af0ecb76dff71baa74d13334",
    "sequence": 1,
    "recent_sequences": [
      1
    ],
    "cas": "",
    "value_crc32c": "",
    "channel_set": null,
    "channel_set_history": null,
    "time_saved": "2025-01-17T08:59:34.432954876Z",
    "cluster_uuid": "d4589fb6ac7ee43584955fbf65d197ef",
    "history": {
      "revs": [
        "1-622c50a7af0ecb76dff71baa74d13334"
      ],
      "parents": [
        -1
      ],
      "channels": [
        null
      ]
    }
  }
}
```
also changed the revision for good measure.

+ We can simply make a request to /db1/2
+ Skip delete

## Task 4

### Description

- Create a document from Couchbase Server UI
- Review the revision IDs and explain the different values in revision IDs
- Also the metadata from postman ends with `0000`, with UI it ends with `0006`

### Observations
We have a current revision ID (which changes when the document is updated) and a history of past revision IDs 

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
