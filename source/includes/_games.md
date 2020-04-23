# Games

## GET: All Games

```shell
curl "https://turnej.com/api/games"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "status": "ACTIVE",
    "season_id": 1,
    "player_home_id": 1,
    "player_home_goals": 2,
    "player_away_id": 2,
    "player_away_goals": 2,
    "version": 2,
    "created_at": "2020-04-20T14:06:04.112Z",
    "modified_at": "2020-04-20T14:54:38.015Z"
  },
  {
    "id": 2,
    "status": "ACTIVE",
    "season_id": 2,
    "player_home_id": 1,
    "player_home_goals": 2,
    "player_away_id": 2,
    "player_away_goals": 0,
    "version": 0,
    "created_at": "2020-04-20T14:55:04.839Z",
    "modified_at": null
  }
]
```

This endpoint retrieves all games.

### HTTP Request

`GET https://turnej.com/api/games`

### Query Parameters

| Parameter  | Default | Description                                                       |
| ---------- | ------- | ----------------------------------------------------------------- |
| season     | -       | The id of the seasons to filter the games                         |
| groupstyle | falt    | The style rounds. (structured, flat)                              |
| active     | true    | If set to true, the result will show games with status 'ACTIVE.   |
| inactive   | false   | If set to true, the result will show games with status 'INACTIVE. |
| deleted    | false   | If set to true, the result will show games with status 'DELETED.  |

### Returned Values

| Parameter         | Type       | Description                                      |
| ----------------- | ---------- | ------------------------------------------------ |
| id                | Integer    | The unique id of the game.                       |
| status            | StatusType | The status of the game.                          |
| season_id         | Integer    | The id of the season                             |
| player_home_id    | Integer    | The id of the playes who playes at home.         |
| player_home_goals | Integer    | The goal count of the player who playes at home. |
| player_away_id    | Integer    | The id of the game who playes at away.           |
| player_away_goals | Integer    | The goal count of the player who playes at away. |
| version           | Integer    | How many times the game has been changed.        |
| created_at        | Date       | The date when the game was created.              |

## GET: Specific Game

```shell
curl "https://turnej.com/api/games/1"
```

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "status": "ACTIVE",
  "season_id": 1,
  "player_home_id": 1,
  "player_home_goals": 2,
  "player_away_id": 2,
  "player_away_goals": 2,
  "version": 2,
  "created_at": "2020-04-20T14:06:04.112Z",
  "modified_at": "2020-04-20T14:54:38.015Z"
}
```

This endpoint retrieves a specific game.

### HTTP Request

`GET http://turnej.com/games/<ID>`

### URL Parameters

| Parameter | TYPE    | Description                    |
| --------- | ------- | ------------------------------ |
| ID        | Integer | The ID of the game to retrieve |

### Returned Values

| Parameter         | Type       | Description                                      |
| ----------------- | ---------- | ------------------------------------------------ |
| id                | Integer    | The unique id of the game.                       |
| status            | StatusType | The status of the game.                          |
| season_id         | Integer    | The id of the season                             |
| player_home_id    | Integer    | The id of the playes who playes at home.         |
| player_home_goals | Integer    | The goal count of the player who playes at home. |
| player_away_id    | Integer    | The id of the game who playes at away.           |
| player_away_goals | Integer    | The goal count of the player who playes at away. |
| version           | Integer    | How many times the game has been changed.        |
| created_at        | Date       | The date when the game was created.              |

## PATCH: Update a Game

```shell
curl 'https://turnej.com/api/games'
  -X PATCH
  -H 'Content-Type: application/json'
  -d '{"player_home_goals": 0, "player_away_goals": 2}'
```

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "status": "ACTIVE",
  "season_id": 1,
  "player_home_id": 1,
  "player_home_goals": 0,
  "player_away_id": 2,
  "player_away_goals": 2,
  "version": 1,
  "created_at": "2020-04-20T14:06:04.112Z",
  "modified_at": "2020-04-20T14:54:38.015Z"
}
```

This endpoint updates a game.

### HTTP Request

`PATCH http://turnej.com/games/<ID>`

### URL Parameters

| Parameter | TYPE    | Description                    |
| --------- | ------- | ------------------------------ |
| ID        | Integer | The ID of the game to retrieve |

### Body Parameters

| Parameter         | Type    | Description                                      |
| ----------------- | ------- | ------------------------------------------------ |
| player_home_goals | Integer | The goal count of the player who playes at home. |
| player_away_goals | Integer | The goal count of the player who playes at away. |

### Returned Values

| Parameter         | Type       | Description                                      |
| ----------------- | ---------- | ------------------------------------------------ |
| id                | Integer    | The unique id of the game.                       |
| status            | StatusType | The status of the game.                          |
| season_id         | Integer    | The id of the season                             |
| player_home_id    | Integer    | The id of the playes who playes at home.         |
| player_home_goals | Integer    | The goal count of the player who playes at home. |
| player_away_id    | Integer    | The id of the game who playes at away.           |
| player_away_goals | Integer    | The goal count of the player who playes at away. |
| version           | Integer    | How many times the game has been changed.        |
| created_at        | Date       | The date when the game was created.              |
