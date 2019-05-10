# blimp
Blimp

## Getting Started and Tests

### Setting up Local Postgres Instance

```
brew install postgresql
psql postgres
```

Once connected to Postgres instance:

1. Create a user:

```
postgres=# CREATE ROLE me WITH LOGIN PASSWORD 'password';
postgres=# ALTER ROLE me CREATEDB;
\q
```

2. Reconnect to the DB
```
psql -d postgres -U me
```

3. Create DB and insert some fake data:
```
postgres=> CREATE DATABASE blimp;
postgres=> \c blimp
blimp=>
CREATE TABLE dashboard (
  ID SERIAL PRIMARY KEY,
  url VARCHAR(30),
  content VARCHAR(30)
);
INSERT INTO dashboard (url, content)
  VALUES ('bar', 'I am dashboard bar'), ('foo', 'I am dashboard foo');
```

4. Confirm creation of data:

```
SELECT * FROM dashboard;
```

Install all dependencies

```
npm install
```

To Run:

First start up postgres instance

```
brew services start postgresql
```

```
npm start
```

Running tests:

```
npm run test
```

Test Coverage Report:

```
npm run cov
```
