# Tasks

## Task 1

### Description

- Setup SGW using setup 1
- Use Postman to check if SGW is working (use Admin PORT)

### Observations
couldnt do it because config2 has admin interface and config1 which belongs tp setup1 doesnt have admin interface.



## Task 2

### Description

- Setup SGW using setup 2
- Create a Database using Postman
- Create a Document using Postman
- Get the document using Postman

### Observations
creating a database using postman


created a document using postman

{
    "id": "2",
    "ok": true,
    "rev": "1-622c50a7af0ecb76dff71baa74d13333"
}
got a doc using postman

{
    "_id": "1",
    "_rev": "1-8a4f0130acffc27a65a4137f1051bed5",
    "name": "Ramya",
    "task": "2"
}

## Task 3

### Description

- This task continues from the previous task
- Create a dummy document from CB UI
- Get the document contents using Postman
- Delete the document using Postman

### Observations

created using cb ui and got a doc using postman

{
    "_id": "1",
    "_rev": "1-8a4f0130acffc27a65a4137f1051bed5",
    "name": "Ramya",
    "task": "2"
}



## Task 4

### Description

- Create a document from Couchbase Server UI
- Review the revision IDs and explain the different values in revision IDs

### Observations




{
    "Name": "Lol DOc 3",
    "_id": "3",
    "_rev": "1-4f7edf31646f45518ce507456daad34a",
    "task": "4"
}

before

{
  "meta": {
    "id": "3",
    "rev": "2-181b71697bd900000000000002000006",
    "expiration": 0,
    "flags": 33554438,
    "type": "json"
  },
  "xattrs": {
    "_mou": {
      "cas": "0x0000d97b69711b18",
      "pCas": "0x0000c27b69711b18"
    },
    "_sync": {
      "cas": "0x0000d97b69711b18",
      "channel_set": null,
      "channel_set_history": null,
      "cluster_uuid": "2e75d5541c2acfc3c21a9f6077558faf",
      "history": {
        "channels": [
          null
        ],
        "parents": [
          -1
        ],
        "revs": [
          "1-4f7edf31646f45518ce507456daad34a"
        ]
      },
      "recent_sequences": [
        3
      ],
      "rev": "1-4f7edf31646f45518ce507456daad34a",
      "sequence": 3,
      "time_saved": "2025-01-17T09:39:39.144416838Z",
      "value_crc32c": "0x27c5d6de"
    }
  }
}

after
{
  "meta": {
    "id": "3",
    "rev": "4-181b721d8ceb00000000000002000006",
    "expiration": 0,
    "flags": 33554438,
    "type": "json"
  },
  "xattrs": {
    "_mou": {
      "cas": "0x0000eb8c1d721b18",
      "pCas": "0x0000bf8c1d721b18"
    },
    "_sync": {
      "cas": "0x0000eb8c1d721b18",
      "channel_set": null,
      "channel_set_history": null,
      "cluster_uuid": "2e75d5541c2acfc3c21a9f6077558faf",
      "history": {
        "channels": [
          null,
          null
        ],
        "parents": [
          -1,
          0
        ],
        "revs": [
          "1-4f7edf31646f45518ce507456daad34a",
          "2-f020b9c93c4eb48402e86c47dde63b22"
        ]
      },
      "recent_sequences": [
        3,
        4
      ],
      "rev": "2-f020b9c93c4eb48402e86c47dde63b22",
      "sequence": 4,
      "time_saved": "2025-01-17T09:52:32.52470596Z",
      "value_crc32c": "0x828444a0"
    }
  }
}







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

1. false, false
when doc is created after creating database with false false ,
we cannot retrieve the doc becayse docs are not imported

2. with shared access true , import docs = false
{
    "_id": "2",
    "_rev": "1-6c09ee187cece3ab2da390476ac6b48f",
    "click": "to edit",
    "with JSON": "there are no reserved field names"
}
we can get the doc that's created after the db


3. enable_shared_bucket_access: false, import_docs: true
we cannot import docs if shared access is denied
{"error":"Bad Request","reason":"1 errors:\nInvalid configuration - import_docs enabled, but enable_shared_bucket_access not enabled"}%                             
 
4. enable_shared_bucket_access: true, import_docs: true
we can get docs that are added before creation and after creation 



