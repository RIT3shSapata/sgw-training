# Tasks

## Task 1

### Description

- Setup SGW using setup 1
- Use Postman to check if SGW is working (use Admin PORT)

### Observations

Procedure I did for TASK 1:

-Created main couchbase cluster
-Create a new bucket
-Create a new user for syncgateway and assign permissions in security port
-Take the config.json and put it in a directory (for eg in documents)
-Pull the couchbase syncgateway image
-Start the couchbase syncgatewa container
-Use curl to make a PUT request to configure the syncgateway. (Run the curl command inside the syncgateway container)
```
curl --location --request PUT 'http://127.0.0.1:4985/db/' --header 'Content-Type: application/json' --data-raw '{"bucket": "syncgateway","num_index_replicas": 0, "enable_shared_bucket_access": true,
 "import_docs": true}' -u rahulvk007
 ```
![alt text](image-8.png)

SOLUTION FOR TASK 1: EDIT config1.json and add this

```
"api": {
    "admin_interface": "0.0.0.0:4985"
  }
  ```

## Task 2

### Description

- Setup SGW using setup 2
- Create a Database using Postman
- Create a Document using Postman
- Get the document using Postman

### Observations

![alt text](image.png)

![alt text](image-1.png)

CREATE DATABASE

![alt text](image-3.png)

UPDATE TO ENABLE SHARED BUCKET ACCESS AND IMOORT DOCS

![alt text](image-4.png)

CREATE DOCUMENT

![alt text](image-5.png)

GET DOCUMENT

![alt text](image-6.png)


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
