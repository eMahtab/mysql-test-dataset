# MySQL test dataset

## Dataset : users-and-messages

https://github.com/eMahtab/mysql-test-dataset/blob/main/users-and-messages/test_database.zip

This MySQL dataset is exported from a mysql database named `test`.
The `test` database contains two tables `users` and `messages`

### Dataset Size :

**users table = 10 Million records**

**messages table = 100 Million records**

#### Schema  : 
**The tables were originally created using below DDL statements :**

```sql
CREATE TABLE users (
    id BIGINT,
    name VARCHAR(50),
    username VARCHAR(30),
    PRIMARY KEY (id)
);

CREATE TABLE messages (
    id BIGINT,
    sender_id BIGINT,
    recipient_id BIGINT,
    message TEXT,
    created_at DATETIME NOT NULL,
    edited_at DATETIME DEFAULT NULL,
    deleted_at DATETIME DEFAULT NULL,
    PRIMARY KEY (id),
    FOREIGN KEY (sender_id) REFERENCES users(id),
    FOREIGN KEY (recipient_id) REFERENCES users(id)
);
```

