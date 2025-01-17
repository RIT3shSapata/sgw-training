# Tasks

## Task 1

### Description

- Setup SGW using setup 1
- Use Postman to check if SGW is working (use Admin PORT)

### Observations
```
  "api": {
    "admin_interface": "0.0.0.0:4985"
  }
  there only in config2 and not config1
  therefore postman works only for setup2 and not setup1
  ```

## Task 2

### Description

- Setup SGW using setup 2
- Create a Database using Postman
- Create a Document using Postman
- Get the document using Postman

### Observations
```
Database Creation Using Postman:
http://127.0.0.1:4985/db1/
http://127.0.0.1:4985/_all_dbs
[
    "db"
]

Document using Postman:
http://127.0.0.1:4985/db/?name=saimirra

Get the document using Postman:
{
    "db_name": "db",
    "update_seq": 2,
    "committed_update_seq": 2,
    "instance_start_time": 1737106749563621,
    "compact_running": false,
    "purge_seq": 0,
    "disk_format_version": 0,
    "state": "Online",
    "server_uuid": "4ff08613deec312686f6aacb5053718b"
}
```
## Task 3

### Description

- This task continues from the previous task
- Create a dummy document from CB UI
- Get the document contents using Postman
- Delete the document using Postman

### Observations
```
- Create a dummy document from CB UI
- Get the document contents using Postman
{
    "db_name": "db",
    "update_seq": 4,
    "committed_update_seq": 4,
    "instance_start_time": 1737106749563621,
    "compact_running": false,
    "purge_seq": 0,
    "disk_format_version": 0,
    "state": "Online",
    "server_uuid": "4ff08613deec312686f6aacb5053718b"
}
```
## Task 4

### Description
```
- Create a document from Couchbase Server UI
- Review the revision IDs and explain the different values in revision IDs
```


### Observations
```
"rev": "2-181b7266f06900000000000002000006"
"rev": "1-6c09ee187cece3ab2da390476ac6b48f"
change in revision id with every fetch
```

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
```
1. enable_shared_bucket_access: false, import_docs: false
Import docs is false
2. enable_shared_bucket_access: false, import_docs: true
Import docs is properly ignored, warning logged
3. enable_shared_bucket_access: true, import_docs: false
Node omitted from import processing, supported for workload isolation
4. enable_shared_bucket_access: true, import_docs: true
Node participates in import processing and is  assigned partitions.
```