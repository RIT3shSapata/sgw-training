# Tasks

## Task 1

### Description

- Setup SGW using setup 1
- Use Postman to check if SGW is working (use Admin PORT)

### Observations
![alt text](<Screenshot 2025-01-17 at 2.18.32 PM.png>)
## Task 2

### Description

- Setup SGW using setup 2
- Create a Database using Postman
- Create a Document using Postman
- Get the document using Postman

### Observations
![alt text](<Screenshot 2025-01-17 at 3.22.56 PM.png>)
![alt text](<Screenshot 2025-01-17 at 3.23.30 PM.png>)
![alt text](<Screenshot 2025-01-17 at 3.23.54 PM.png>)


## Task 3

### Description

- This task continues from the previous task
- Create a dummy document from CB UI
- Get the document contents using Postman
- Delete the document using Postman

### Observations

- Created dummy document, gave it an id of 2
![alt text](<Screenshot 2025-01-17 at 3.28.11 PM.png>)


## Task 4

### Description

- Create a document from Couchbase Server UI
- Review the revision IDs and explain the different values in revision IDs

### Observations

Revision ID consists of a generation number (incrementing with each update) and a hash of the document's content. The generation number tracks how many times the document has been modified, while the hash uniquely identifies the content.

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

1. Sync Gateway does not have direct access to the Couchbase Server bucket, and it won't import existing documents from Couchbase. Sync Gateway works in isolation.
2. Sync Gateway doesn't have direct access to the Couchbase bucket, but it will import documents from the bucket into Sync Gateway. Documents are imported into Sync Gateway but no changes can be made directly in Couchbase Server from Sync Gateway.
3. Sync Gateway has direct access to the Couchbase bucket, but it won't import existing documents from Couchbase into Sync Gateway. Sync Gateway syncs new documents to Couchbase Server, but does not manage or import existing documents from the bucket.
4. Sync Gateway has direct access to the Couchbase bucket and will import existing documents into Sync Gateway. Sync Gateway fully manages documents in Couchbase Server, including syncing, updating, and accessing the documents both ways.