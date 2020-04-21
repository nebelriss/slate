# Users

## Get All Users

```shell
curl "https://turnej.com/api/users"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "status": "ACTIVE",
    "name": "First User",
    "username": "first-user",
    "password": "password",
    "version": 0,
    "created_at": "2020-04-20T11:36:03.988Z",
    "modified_at": null
  },
  {
    "id": 2,
    "status": "ACTIVE",
    "name": "Second User",
    "username": "second",
    "password": "password",
    "version": 0,
    "created_at": "2020-04-20T17:09:38.593Z",
    "modified_at": null
  }
]
```

This endpoint retrieves all users.

### HTTP Request

`GET https://turnej.coms/api/users`

### Query Parameters

| Parameter | Default | Description                                                       |
| --------- | ------- | ----------------------------------------------------------------- |
| active    | true    | If set to true, the result will show users with status 'ACTIVE.   |
| inactive  | false   | If set to true, the result will show users with status 'INACTIVE. |
| deleted   | false   | If set to true, the result will show users with status 'DELETED.  |

## Get a Specific User

```shell
curl "https://turnej.com/api/users/1"
```

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "status": "ACTIVE",
  "name": "First User",
  "username": "first-user",
  "password": "password",
  "version": 0,
  "created_at": "2020-04-20T11:36:03.988Z",
  "modified_at": null
}
```

This endpoint retrieves a specific user.

### HTTP Request

`GET http://turnej.com/users/<ID>`

### URL Parameters

| Parameter | TYPE    | Description                    |
| --------- | ------- | ------------------------------ |
| ID        | Integer | The ID of the user to retrieve |

## Create a User

```shell
curl 'https://turnej.com/api/users'
  -d '{"name": "A User"}'
  -H 'Content-Type: application/json'
```

This endpoint creates a user.

### HTTP Request

`GET http://turnej.com/users`

### Body Parameters

## Update a User

## Delete a Specific Kitten

```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require("kittn");

let api = kittn.authorize("meowmeowmeow");
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted": ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

| Parameter | Description                    |
| --------- | ------------------------------ |
| ID        | The ID of the kitten to delete |
