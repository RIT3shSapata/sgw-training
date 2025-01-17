# Tasks

## Task 1

### Description

- Setup SGW using setup 1
- Use Postman to check if SGW is working (use Admin PORT)

### Observations

Output of last command: (on terminal)

```  {"couchdb":"Welcome","vendor":{"name":"Couchbase Sync Gateway","version":"3.2"},"version":"Couchbase Sync Gateway/3.2.1(15;release) EE","persistent_config":true}  ```

_Steps:_

Used config2 instead, where admin api is mentioned. Also, in config2 changed the bootstrap/server to "couchbase://172.17.0.2", and the bootstrap/password.

Output on Postman:
```
{
    "ADMIN": true,
    "couchdb": "Welcome",
    "vendor": {
        "name": "Couchbase Sync Gateway",
        "version": "3.2"
    },
    "version": "Couchbase Sync Gateway/3.2.1(15;release) EE",
    "persistent_config": true
}
```

## Task 2

### Description

- Setup SGW using setup 2
- Create a Database using Postman
- Create a Document using Postman
- Get the document using Postman


Steps:

1. To make a db. just changed passwords (username: Administrator, password: password) and made them consistent. Also, in config2.json changed the bootstrap/server to "couchbase://10.5.0.2" back.


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
