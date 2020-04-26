# Players

## GET: All Players

```shell
curl "https://turnej.com/api/players"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "status": "ACTIVE",
    "user_id": 1,
    "name": "Player_one",
    "version": 0,
    "created_at": "2020-04-20T11:55:07.326Z",
    "modified_at": null
  },
  {
    "id": 2,
    "status": "ACTIVE",
    "user_id": 1,
    "name": "Player two",
    "version": 0,
    "created_at": "2020-04-20T11:39:59.769Z",
    "modified_at": null
  }
]
```

This endpoint retrieves all players.

### HTTP Request

`GET https://turnej.com/api/players`

### Query Parameters

| Parameter | Default | Description                                                        |
| --------- | ------- | ------------------------------------------------------------------ |
| active    | true    | If set to true, the result will show player with status 'ACTIVE.   |
| inactive  | false   | If set to true, the result will show player with status 'INACTIVE. |
| deleted   | false   | If set to true, the result will show player with status 'DELETED.  |

### Returned Values

| Parameter   | Type       | Description                                    |
| ----------- | ---------- | ---------------------------------------------- |
| id          | Integer    | The unique id of the player.                   |
| status      | StatusType | The status of the player.                      |
| user_id     | Integer    | The ID of the assosiated user                  |
| name        | String     | The full name of the player.                   |
| version     | Integer    | How many times the player has been changed.    |
| created_at  | Date       | The date when the player was created.          |
| modified_at | Date       | The date when the player was last time changed |

## GET: Specific Player

```shell
curl "https://turnej.com/api/players/1"
```

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "status": "ACTIVE",
  "user_id": 1,
  "name": "Player_one",
  "version": 0,
  "created_at": "2020-04-20T11:55:07.326Z",
  "modified_at": null
}
```

This endpoint retrieves a specific player.

### HTTP Request

`GET http://turnej.com/players/<ID>`

### URL Parameters

| Parameter | TYPE    | Description                      |
| --------- | ------- | -------------------------------- |
| ID        | Integer | The ID of the player to retrieve |

### Returned Values

| Parameter   | Type       | Description                                    |
| ----------- | ---------- | ---------------------------------------------- |
| id          | Integer    | The unique id of the player.                   |
| status      | StatusType | The status of the player.                      |
| user_id     | Integer    | The ID of the assosiated user                  |
| name        | String     | The full name of the player.                   |
| version     | Integer    | How many times the player has been changed.    |
| created_at  | Date       | The date when the player was created.          |
| modified_at | Date       | The date when the player was last time changed |

## POST: Create a Player

```shell
curl 'https://turnej.com/api/players'
  -X POST
  -H 'Content-Type: application/json'
  -d '{"name": "player_one"}'
```

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "status": "ACTIVE",
  "user_id": 1,
  "name": "Player_one",
  "version": 0,
  "created_at": "2020-04-20T11:55:07.326Z",
  "modified_at": null
}
```

This endpoint creates a player.

### HTTP Request

`POST http://turnej.com/players`

### Body Parameters

| Parameter | Type   | Description                 |
| --------- | ------ | --------------------------- |
| name      | String | The full name of the player |

### Returned Values

| Parameter   | Type       | Description                                    |
| ----------- | ---------- | ---------------------------------------------- |
| id          | Integer    | The unique id of the player.                   |
| status      | StatusType | The status of the player.                      |
| user_id     | Integer    | The ID of the assosiated user                  |
| name        | String     | The full name of the player.                   |
| version     | Integer    | How many times the player has been changed.    |
| created_at  | Date       | The date when the player was created.          |
| modified_at | Date       | The date when the player was last time changed |

## PATCH: Update a Player

```shell
curl 'https://turnej.com/api/players/1'
  -X PATCH
  -H 'Content-Type: application/json'
  -d '{"username": "player_two"}'
```

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "status": "ACTIVE",
  "user_id": 1,
  "name": "Player_two",
  "version": 0,
  "created_at": "2020-04-20T11:55:07.326Z",
  "modified_at": null
}
```

This endpoint updates a player.

### HTTP Request

`PATCH http://turnej.com/players/<ID>`

### URL Parameters

| Parameter | Description                    |
| --------- | ------------------------------ |
| ID        | The ID of the player to delete |

### Body Parameters

| Parameter | Type   | Description                          |
| --------- | ------ | ------------------------------------ |
| username  | String | The username of the player           |
| password  | String | Hash of the password from the player |

### Returned Values

| Parameter   | Type       | Description                                    |
| ----------- | ---------- | ---------------------------------------------- |
| id          | Integer    | The unique id of the player.                   |
| status      | StatusType | The status of the player.                      |
| user_id     | Integer    | The ID of the assosiated user                  |
| name        | String     | The full name of the player.                   |
| version     | Integer    | How many times the player has been changed.    |
| created_at  | Date       | The date when the player was created.          |
| modified_at | Date       | The date when the player was last time changed |

## DELTETE: Specific Player

```shell
curl 'https://turnej.com/api/players/1'
  -X DELETE
```

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "status": "ACTIVE",
  "user_id": 1,
  "name": "Player_one",
  "version": 0,
  "created_at": "2020-04-20T11:55:07.326Z",
  "modified_at": null
}
```

This endpoint does deletes a player.  
It does not delete it from the database. It only sets the status of the player to 'DELETED'.

### HTTP Request

`DELETE https://turnej.com/players/<ID>`

### URL Parameters

| Parameter | Description                    |
| --------- | ------------------------------ |
| ID        | The ID of the player to delete |

### Returned Values

| Parameter   | Type       | Description                                    |
| ----------- | ---------- | ---------------------------------------------- |
| id          | Integer    | The unique id of the player.                   |
| status      | StatusType | The status of the player.                      |
| user_id     | Integer    | The ID of the assosiated user                  |
| name        | String     | The full name of the player.                   |
| version     | Integer    | How many times the player has been changed.    |
| created_at  | Date       | The date when the player was created.          |
| modified_at | Date       | The date when the player was last time changed |
