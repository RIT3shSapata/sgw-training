# Tasks

## Task 1

### Description

- Setup SGW using setup 1
- Use Postman to check if SGW is working (use Admin PORT)

### Observations

<img width="1671" alt="image" src="https://github.com/user-attachments/assets/9b75a943-50df-4336-b053-307e13b681fd" />
Added api -> admin interface section
Response
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

### Observations
<img width="1623" alt="image" src="https://github.com/user-attachments/assets/f66ca281-f9f0-44ba-a2d5-44397f101dc3" />

<img width="1569" alt="image" src="https://github.com/user-attachments/assets/201de84a-a8c9-418e-99f8-57b520a40ba9" />

<img width="1610" alt="image" src="https://github.com/user-attachments/assets/649968dd-e209-4102-92c2-b59fe6da70fc" />


## Task 3

### Description

- This task continues from the previous task
- Create a dummy document from CB UI
- Get the document contents using Postman
- Delete the document using Postman

### Observations
Need to update the DB before we can get the doc
<img width="1564" alt="image" src="https://github.com/user-attachments/assets/776b6b5e-3a6e-47bd-856b-ec5a736c5cdd" />

<img width="1598" alt="image" src="https://github.com/user-attachments/assets/2f92d480-b944-4e5f-a240-065ae72279db" />


## Task 4

### Description

- Create a document from Couchbase Server UI
- Review the revision IDs and explain the different values in revision IDs

### Observations
Since sync gateway also processes the document, it increments the revision id to 2.
<img width="1229" alt="image" src="https://github.com/user-attachments/assets/ddfaabe9-5cc4-4b33-9d45-b6047109a63f" />

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
1. <img width="1510" alt="image" src="https://github.com/user-attachments/assets/fcb9c124-c8f4-49fd-9d01-e6a2074d289c" />
Changes won't be accessible
2. Won't let you change <img width="1302" alt="image" src="https://github.com/user-attachments/assets/efe099a8-545e-4687-ac16-96ee418332e7" />

3. <img width="1225" alt="image" src="https://github.com/user-attachments/assets/751e1498-4e48-4e37-80ca-7f96edb7e614" />
The metadata will get updated only when we access the document
4. <img width="1288" alt="image" src="https://github.com/user-attachments/assets/3beb0944-e626-464e-b4d2-ac490c10608f" />
