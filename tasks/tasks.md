# Tasks

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
