# Tasks

## Task 1

### Description

- Setup SGW using setup 1
- Use Postman to check if SGW is working (use Admin PORT)

### Observations
<img width="851" alt="image" src="https://github.com/user-attachments/assets/0692feda-e03c-48f6-9415-901932e52541" />

## Task 2

### Description

- Setup SGW using setup 2
- Create a Database using Postman
- Create a Document using Postman
- Get the document using Postman

### Observations
- Create DB:
<img width="859" alt="image" src="https://github.com/user-attachments/assets/37aa3ffd-47d5-49b9-a64f-e2e25be5ee34" />
- Create Document:
<img width="856" alt="image" src="https://github.com/user-attachments/assets/8f0fa191-95ad-4685-ab5b-2a6f5f280e5c" />
<img width="1426" alt="image" src="https://github.com/user-attachments/assets/335bec44-9048-4b9c-9287-8b8459a5c522" />
- Get document
Had to correct the document id in request from 2 to 1
<img width="844" alt="image" src="https://github.com/user-attachments/assets/55a87ee9-9945-441d-9306-8ecdb8bedda1" />


## Task 3

### Description

- This task continues from the previous task
- Create a dummy document from CB UI
- Get the document contents using Postman
- Delete the document using Postman

### Observations
- Made a dummy document with _id:11 and "abcd":1234
<img width="643" alt="image" src="https://github.com/user-attachments/assets/0e3ec9de-5d72-47a8-a00a-942a233e2f2f" />
- Update DB to import new doc
<img width="852" alt="image" src="https://github.com/user-attachments/assets/1dc4842c-31b9-4817-a62b-0b12156fb2d7" />
- Get doc
<img width="840" alt="image" src="https://github.com/user-attachments/assets/6740e99b-acd9-4e79-bee4-320ff513ed22" />

## Task 4

### Description

- Create a document from Couchbase Server UI
- Review the revision IDs and explain the different values in revision IDs


### Observations
I have created 1 doc through postman (id:1) and 2 through CB UI(id: 11 and 21). Each doc has a meta rev ID and a bunch of XATTRS rev IDs, one for each update to the doc. I'm guessing the XATTRS rev IDs are for each time a doc update is processed by sync gateway?

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
For (4.) we've already seen the effects of true,true - document updates are reflected in the SGW DB on update. Let's try document updates with each config

1. false, false - 
<img width="1488" alt="image" src="https://github.com/user-attachments/assets/b1d16992-c784-4c72-8023-e923cd1571b8" />
error object not found in CB UI

2. false, true - same error as (1)
3. true, false -
<img width="863" alt="image" src="https://github.com/user-attachments/assets/c347f300-e2c3-4910-9889-43ba999f0d8b" />
it is not allowed, which makes sense as it doesn't make sense to import doc when you dont have shared bucket access.

Now let's try document create on CB with each config

1. false, false -
<img width="853" alt="image" src="https://github.com/user-attachments/assets/84b36b48-364e-4d27-aa63-a06a06fabc97" />
2. false, true -
  
3. true, false - bad request
