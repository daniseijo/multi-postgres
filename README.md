# Multi Postgres

Based on [postgres:10-alpine](https://github.com/docker-library/postgres/blob/cc305ee1c59d93ac1808108edda6556b879374a4/10/alpine/Dockerfile).

This is a first version so it doesn't handle a lot of errors.

To use this image add the following environment variables:

```
PG_DATABASES=database1,database2,database3
PG_USERS=user1,user2,user3
PG_PASSWORDS=password1,password2,password3
```

Be sure to have the same number of databases, users and passwords.

docker-compose.yml example:

```yml
version: "3.5"
services:
  multi-db:
    image: daniseijo/multi-postgres
    ports:
      - 5432:5432
    environment:
      PG_DATABASES: database1,database2,database3
      PG_USERS: user1,user2,user3
      PG_PASSWORDS: password1,password2,password3
```
