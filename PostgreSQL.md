# PostgreSQL

## Setup

By default on unix installations a user "postgres" is created and granted administration access.
Initial setup can be done running a shell with privileges from the "postgres" system user.

### Password

For every user that we add, we need to set the password.

```sql
ALTER USER postgres WITH PASSWORD 'password';
```

## Database Grants

[From SO](https://stackoverflow.com/questions/67276391/why-am-i-getting-a-permission-denied-error-for-schema-public-on-pgadmin-4)

PostgreSQL 15 also revokes the CREATE permission from all users except a database owner from the public (or default) schema.

\connect "CashPoint24"
GRANT ALL ON SCHEMA public TO "CashPoint24";

## Dump & Restore

```sh
pg_dump <db name> -e pg_catalog.plpgsql -F c --no-owner --no-privileges -f /tmp/<db name>.dump
pg_restore -h localhost --username <user name> --password -1 -d <db name> /tmp/<db name>.dump
```
