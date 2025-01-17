# Tasks - Goutham Krishnan

## Task 1

### Description

- Setup SGW using setup 1
- Use Postman to check if SGW is working (use Admin PORT)

### Observations

- Connected to the sgw using the config file with the username and password after creating the user and the password.
- Postman couldn't ping the localhost on the admin port. Included the admin interface port number in the config2.json file.

## Task 2

### Description

- Setup SGW using setup 2
- Create a Database using Postman
- Create a Document using Postman
- Get the document using Postman

### Observations

- Created a docker network and then the sgw for the nodes composed using docker compose yaml file.
- Created a database db1 in the travel-sample bucket
- created the document: Output:
- "id": 1, "ok": True, "rev": "1-622c50a7af0ecb76dff71baa74d13333"
- Get document executed. Output: 
- {
    "db_name": "db1",
    "update_seq": 1,
    "committed_update_seq": 1,
    "instance_start_time": 1737106922186214,
    "compact_running": false,
    "purge_seq": 0,
    "disk_format_version": 0,
    "state": "Online",
    "server_uuid": "b7d539a04e4f19cdefc6db880a471ca3"
}

## Task 3

### Description

- This task continues from the previous task
- Create a dummy document from CB UI
- Get the document contents using Postman
- Delete the document using Postman

### Observations

- Created a document in the default scope and collection of the travel-sample bucket using the UI.
- Get document executed from postman. Set the "enable_shared_bucket" field to true and "import_docs" to true in the collections config of the api.

## Task 4

### Description

- Create a document from Couchbase Server UI
- Review the revision IDs and explain the different values in revision IDs

### Observations

- Created a document in the travel-sample bucket.
- Initial revision ID present at the start.
- Inside the xattr object, we have revision id indicating the updates made to the document.
- Perform an update on the document using postman, a new revision id is seen. The first digit indicating the number of revisions made.

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

1. Cannot get the document through sgw. Import docs set to false. Doesn't work.
2. Import docs property ignored. Cannot get the document. Gets a warning message that shared bucket access is set to false.
3. Cannot get the doc through sgw.
4. Can get the doc through sgw. Works.
