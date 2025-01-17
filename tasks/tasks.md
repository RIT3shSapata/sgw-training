# Tasks

## Task 1

### Description

- Setup SGW using setup 1
- Use Postman to check if SGW is working (use Admin PORT)

### Observations
sync gateway is set up with just one node and can be accessed from console and UI and also postman with just welcome response.
The provided collection had to be imported and examples can be used.

## Task 2

### Description

- Setup SGW using setup 2
- Create a Database using Postman
- Create a Document using Postman
- Get the document using Postman

### Observations
There was an issue then i saw that the cluster had to be created thats why it was crashing and had to be restarted every now and then. Also the variables of host and authorization to finally, the auth had to be selected for each example manually.
create database added some docs in UI and also create document.
get document works 
## Task 3

### Description

- This task continues from the previous task
- Create a dummy document from CB UI
- Get the document contents using Postman
- Delete the document using Postman

### Observations
but when doc created from UI get doc wont work because import is off so sgw wont import docs created in cb ui automatically even though shared bucket exist.
update database had to be ran with true true config for making changes 
now get doc works

## Task 4

### Description

- Create a document from Couchbase Server UI
- Review the revision IDs and explain the different values in revision IDs

### Observations
Revision id  at the very top is for doc itself in server, furhter revision ids are within _sync gateway so it must be sgw's copies .
and as to why its in an array its cause multiple sync gateway can connect to one.
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
1. works, means that docs created on mobile stay there and can be accessed but not the ones from UI
2. fails
3. works, sgw wont import all documents automatically , only those that got accessed.
4. works, imports all docs proactively.

