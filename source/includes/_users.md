# Users

## GET: All Users

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

`GET https://turnej.com/api/users`

### Query Parameters

| Parameter | Default | Description                                                       |
| --------- | ------- | ----------------------------------------------------------------- |
| active    | true    | If set to true, the result will show users with status 'ACTIVE.   |
| inactive  | false   | If set to true, the result will show users with status 'INACTIVE. |
| deleted   | false   | If set to true, the result will show users with status 'DELETED.  |

### Returned Values

| Parameter  | Type       | Description                               |
| ---------- | ---------- | ----------------------------------------- |
| id         | Integer    | The unique id of the user.                |
| status     | StatusType | The status of the user.                   |
| name       | String     | The full name of the user.                |
| password   | String     | The password of the user.                 |
| username   | String     | The username of the user.                 |
| version    | Integer    | How many times the user has been changed. |
| created_at | Date       | The date when the user was created.       |

## GET: Specific User

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

### Returned Values

| Parameter  | Type       | Description                               |
| ---------- | ---------- | ----------------------------------------- |
| id         | Integer    | The unique id of the user.                |
| status     | StatusType | The status of the user.                   |
| name       | String     | The full name of the user.                |
| password   | String     | The password of the user.                 |
| username   | String     | The username of the user.                 |
| version    | Integer    | How many times the user has been changed. |
| created_at | Date       | The date when the user was created.       |

## POST: Create a User

```shell
curl 'https://turnej.com/api/users'
  -X POST
  -H 'Content-Type: application/json'
  -d '{"name": "User Name", "username": "username", "password": "password"}'
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

This endpoint creates a user.

### HTTP Request

`POST http://turnej.com/users`

### Body Parameters

| Parameter | Type   | Description                        |
| --------- | ------ | ---------------------------------- |
| name      | String | The full name of the user          |
| username  | String | The username of the user           |
| password  | String | Hash of the password from the user |

### Returned Values

| Parameter  | Type       | Description                               |
| ---------- | ---------- | ----------------------------------------- |
| id         | Integer    | The unique id of the user.                |
| status     | StatusType | The status of the user.                   |
| name       | String     | The full name of the user.                |
| password   | String     | The password of the user.                 |
| username   | String     | The username of the user.                 |
| version    | Integer    | How many times the user has been changed. |
| created_at | Date       | The date when the user was created.       |

## PATCH: Update a User

```shell
curl 'https://turnej.com/api/users'
  -X PATCH
  -H 'Content-Type: application/json'
  -d '{"username": "username", "password": "password"}'
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

This endpoint update a user.

### HTTP Request

`PATCH http://turnej.com/users`

### Body Parameters

| Parameter | Type   | Description                        |
| --------- | ------ | ---------------------------------- |
| username  | String | The username of the user           |
| password  | String | Hash of the password from the user |

### Returned Values

| Parameter  | Type       | Description                               |
| ---------- | ---------- | ----------------------------------------- |
| id         | Integer    | The unique id of the user.                |
| status     | StatusType | The status of the user.                   |
| name       | String     | The full name of the user.                |
| password   | String     | The password of the user.                 |
| username   | String     | The username of the user.                 |
| version    | Integer    | How many times the user has been changed. |
| created_at | Date       | The date when the user was created.       |

## DELTETE: Specific User

```shell
curl 'https://turnej.com/api/users/1'
  -X DELETE
```

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "status": "DELETED",
  "name": "First User",
  "username": "first-user",
  "password": "password",
  "version": 0,
  "created_at": "2020-04-20T11:36:03.988Z",
  "modified_at": null
}
```

This endpoint does delete a user.  
It does not delete it from the database. It only sets the status of the user to 'DELETED'.

### HTTP Request

`DELETE https://turnej.com/users/<ID>`

### URL Parameters

| Parameter | Description                  |
| --------- | ---------------------------- |
| ID        | The ID of the user to delete |

### Returned Values

| Parameter  | Type       | Description                               |
| ---------- | ---------- | ----------------------------------------- |
| id         | Integer    | The unique id of the user.                |
| status     | StatusType | The status of the user.                   |
| name       | String     | The full name of the user.                |
| password   | String     | The password of the user.                 |
| username   | String     | The username of the user.                 |
| version    | Integer    | How many times the user has been changed. |
| created_at | Date       | The date when the user was created.       |
