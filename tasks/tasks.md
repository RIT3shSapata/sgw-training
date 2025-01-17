# Tasks

## Task 1

### Description

- Setup SGW using setup 1
- Use Postman to check if SGW is working (use Admin PORT)
![image](https://github.com/user-attachments/assets/0e59d242-fcf3-4dc4-aee9-3c56ca07a6a2)
had to add api section to config1.json 

### Observations

## Task 2

### Description

- Setup SGW using setup 2
- Create a Database using Postman
<img width="1728" alt="image" src="https://github.com/user-attachments/assets/68e68e86-9cf5-460f-9094-26993fbeb687" />
had to create a bucket called test
- Create a Document using Postman
<img width="1362" alt="image" src="https://github.com/user-attachments/assets/a93ca558-d74d-4aee-a47e-95e1080f75c3" />

- Get the document using Postman
<img width="1356" alt="image" src="https://github.com/user-attachments/assets/922ef9a2-aade-4ed9-849f-c4b8fe4ccd5c" />
had to change doc id from 2 to 1 in the request
### Observations

## Task 3

### Description

- This task continues from the previous task
- Create a dummy document from CB UI
- Get the document contents using Postman
  <img width="1349" alt="image" src="https://github.com/user-attachments/assets/4a997ac9-92e8-4a26-b107-6a06ee77fdca" />
I created the doc id with 77 using UI 
- Delete the document using Postman

### Observations

## Task 4

### Description

- Create a document from Couchbase Server UI
  
- Review the revision IDs and explain the different values in revision IDs
<img width="1343" alt="image" src="https://github.com/user-attachments/assets/4e7df209-c942-4f8f-b0a8-9760c8ba9c98" />
the revision id is 2
this basically acts like a sequence number ( it always monotically increases 
the hash is the snapshot 
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
