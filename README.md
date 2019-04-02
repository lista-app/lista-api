# Lista API - Node.js Client

A Node.js wrapper for Lista REST API. Easily interact with Lista REST API using this library.

[![dependency status](https://david-dm.org/lista-app/lista-api.svg)](https://david-dm.org/lista-app/lista-api)
[![npm version](https://img.shields.io/npm/v/lista-api.svg)](https://www.npmjs.com/package/lista-api)

## Installation

```
npm install --save lista-api
```

## Setup

```js
const Lista = require('lista-api');

const lista = new Lista({
  baseURL: 'http://example.com',
  encoding: 'utf-8'
});
```

## Example

Fetching user lists:

```js
lista.getUserLists({userEmail: "some@example.com"})
  .then(function (response) {
    // handle success
    console.log(response);
  })
  .catch(function (error) {
    // handle error
    console.log(error);
  })
  .then(function () {
    // always executed
  });
```
With async/await:

```js
async function getUserLists() {
  try {
    const response = await lista.getUserLists({userEmail: "some@example.com"});
    console.log(response);
  } catch (error) {
    console.error(error);
  }
}
```

### GET

- `.getUser({userEmail})`
- `.getList({listId})`
- `.getItem({itemId})`
- `.getUserLists({userEmail})`
- `.getListItems({listId})`
- `.getListUsers({listId})`

### POST

- `.createUser({userEmail, userName})`
- `.createList({listName})`
- `.createItem({itemName})`
- `.createUserList({userEmail, listName})`
- `.createListItem({listId, itemName})`
- `.addListUser({userEmail, listId})`

### PUT

- `.checkItem({itemId, checkedBy})`
- `.uncheckItem({itemId})`

### DELETE

- `.deleteList({listId})`
- `.removeListUser({userEmail, listId})`
