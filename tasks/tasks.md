<img width="419" alt="image" src="https://github.com/user-attachments/assets/c7d8159c-9a08-4848-8cd1-f58f8bd1f6bd" /># Tasks

## Task 1

### Description

- Setup SGW using setup 1
- Use Postman to check if SGW is working (use Admin PORT)

### Observations
The admin API works through postman

 ```
"api": {
    "admin_interface": "0.0.0.0:4985"
  },
  ```
  is important in the task

  ![alt text](image-1.png)


## Task 2

### Description

- Setup SGW using setup 2
- Create a Database using Postman
- <img width="1344" alt="image" src="https://github.com/user-attachments/assets/3e62eac9-89b3-464b-b445-3ed8b2fd50d1" />

- Create a Document using Postman
  <img width="1302" alt="image" src="https://github.com/user-attachments/assets/55034ef4-7e76-4b56-915a-a5d156a4f77d" />
  
- Get the document using Postman
  <img width="1298" alt="image" src="https://github.com/user-attachments/assets/2e2ca7f0-7cde-4253-868d-a888365dcea5" />


### Observations
Used postman to complete the tasks. The bucket should already exist before these tasks.

## Task 3

### Description

- This task continues from the previous task
- Create a dummy document from CB UI
  <img width="1598" alt="image" src="https://github.com/user-attachments/assets/e5832486-fcbf-4778-b64e-2f8ca775a1a1" />

- Get the document contents using Postman
  <img width="642" alt="image" src="https://github.com/user-attachments/assets/40e917ac-8d1c-4d8b-b3e3-84350f88972b" />
  <img width="768" alt="image" src="https://github.com/user-attachments/assets/c98d2e5d-448a-4e54-819a-770c2386f06d" />


- Delete the document using Postman

### Observations
- You need to update the database before getting document contents.

## Task 4

### Description

- Create a document from Couchbase Server UI
- Review the revision IDs and explain the different values in revision IDs


<img width="669" alt="image" src="https://github.com/user-attachments/assets/b2ba5c62-cd15-4d1e-b043-02dd71212015" />
<img width="704" alt="image" src="https://github.com/user-attachments/assets/0e224ffd-33eb-4d62-a71c-bdb9ae14ed99" />


### Observations
- The `meta.rev` shows "2-" (e.g., "2-181b7014b66900000000000002000000") because this is the current revision of the document in Couchbase Server.
- The `_sync.rev` shows "1-" (e.g., "1-622c50a7af0ecb76dff71baa74d13333") because this represents the last revision that was processed by Sync Gateway.
 
The revision ID in Couchbase Server shows "2-" because this document has been modified twice:

1. First Generation (1-):
   - When the document was initially created in Couchbase Server

2. Second Generation (2-):
   - When Sync Gateway processed the document and added its metadata (the `_sync` xattr)
   - The act of Sync Gateway adding its synchronization metadata (`_sync` xattr) counts as a modification to the document
   - This modification automatically increments the document's revision number in Couchbase Server


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
1. enable_shared_bucket_access: false, import_docs: false
<img width="1007" alt="image" src="https://github.com/user-attachments/assets/845ca8ab-89a2-4572-831e-c8b6b323da61" />
<img width="419" alt="image" src="https://github.com/user-attachments/assets/738ae85f-529c-4571-88b2-0e0f08f696c0" />

- Sync Gateway can only access documents created through mobile clients
   - XATTRs will be stored in document body (not metadata)
   - Document metadata limit is 20MB (same as document size)
   - Documents written by Couchbase Server:
     * Won't be automatically processed by Import Processing
     * Won't be accessible via Sync Gateway at all
   This is the most restrictive configuration, suitable only for pure mobile-only scenarios.


2. enable_shared_bucket_access: false, import_docs: true
This configuration doesn't make practical sense as import_docs can't work without shared bucket access.
<img width="928" alt="image" src="https://github.com/user-attachments/assets/37904aaa-d7da-4db8-ac36-4e45761a7251" />


3. enable_shared_bucket_access: true, import_docs: false
- Sync Gateway can access both mobile and server-created documents
   - Documents written by Couchbase Server:
     * Will only go through Import Processing when accessed
     * Are accessible via Sync Gateway
     * Won't be automatically imported
   This is good for scenarios where you want selective import of server documents.

4. enable_shared_bucket_access: true, import_docs: true
- Sync Gateway can access both mobile and server-created documents
   - Documents written by Couchbase Server:
     * Will automatically go through Import Processing
     * Are immediately accessible via Sync Gateway
   This is the most open configuration, suitable for active two-way sync between server and mobile.
