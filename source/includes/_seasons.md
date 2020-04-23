# Seasons

## GET: All Seasons

```shell
curl "https://turnej.com/api/seasons"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "status": "ACTIVE",
    "name": "Season 1",
    "event_date": "1970-01-19T08:56:37.337Z",
    "location": "Some Area",
    "completed": false,
    "locked": false,
    "version": 0,
    "created_at": "2020-04-20T15:42:17.058Z",
    "modified_at": null
  },
  {
    "id": 2,
    "status": "ACTIVE",
    "name": "Season 2",
    "event_date": "1970-01-19T08:56:37.337Z",
    "location": "Some Area",
    "completed": false,
    "locked": false,
    "version": 0,
    "created_at": "2020-04-20T15:42:17.058Z",
    "modified_at": null
  }
]
```

This endpoint retrieves all seasons.

### HTTP Request

`GET https://turnej.com/api/seasons`

### Query Parameters

| Parameter | Default | Description                                                         |
| --------- | ------- | ------------------------------------------------------------------- |
| user      |         | If set it gets all the seasons for a specific user                  |
| active    | true    | If set to true, the result will show seasons with status 'ACTIVE.   |
| inactive  | false   | If set to true, the result will show seasons with status 'INACTIVE. |
| deleted   | false   | If set to true, the result will show seasons with status 'DELETED.  |

### Returned Values

| Parameter   | Type       | Description                                                                          |
| ----------- | ---------- | ------------------------------------------------------------------------------------ |
| id          | Integer    | The unique id of the season.                                                         |
| status      | StatusType | The status of the season.                                                            |
| name        | String     | The full name of the season.                                                         |
| event_date  | Date       | The date of the event.                                                               |
| location    | String     | The name of the location.                                                            |
| completed   | Boolean    | If true the season is completed. This means that all games have been also completed. |
| locked      | Boolean    | If the season is locked, then no changes can be made to it.                          |
| version     | Integer    | How many times the season has been changed.                                          |
| created_at  | Date       | The date when the season was created.                                                |
| modified_at | Date       | The date when the season was modified.                                               |

## GET: Specific Season

```shell
curl "https://turnej.com/api/seasons/1"
```

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "status": "ACTIVE",
  "name": "Season 1",
  "event_date": "1970-01-19T08:56:37.337Z",
  "location": "Some Area",
  "completed": false,
  "locked": false,
  "version": 0,
  "created_at": "2020-04-20T15:42:17.058Z",
  "modified_at": null
}
```

This endpoint retrieves a specific season.

### HTTP Request

`GET https://turnej.com/api/seasons/<ID>`

### URL Parameters

| Parameter | TYPE    | Description                      |
| --------- | ------- | -------------------------------- |
| ID        | Integer | The ID of the season to retrieve |

### Returned Value

| Parameter   | Type       | Description                                                                          |
| ----------- | ---------- | ------------------------------------------------------------------------------------ |
| id          | Integer    | The unique id of the season.                                                         |
| status      | StatusType | The status of the season.                                                            |
| name        | String     | The full name of the season.                                                         |
| event_date  | Date       | The date of the event.                                                               |
| location    | String     | The name of the location.                                                            |
| completed   | Boolean    | If true the season is completed. This means that all games have been also completed. |
| locked      | Boolean    | If the season is locked, then no changes can be made to it.                          |
| version     | Integer    | How many times the season has been changed.                                          |
| created_at  | Date       | The date when the season was created.                                                |
| modified_at | Date       | The date when the season was modified.                                               |

## POST: Create a Season

```shell
curl 'https://turnej.com/api/seasons'
  -X POST
  -H 'Content-Type: application/json'
  -d '{"name": "Season name", "location": "Some location", "event_date": "DATE"}'
```

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "status": "ACTIVE",
  "name": "Season 1",
  "event_date": "1970-01-19T08:56:37.337Z",
  "location": "Some Area",
  "completed": false,
  "locked": false,
  "version": 0,
  "created_at": "2020-04-20T15:42:17.058Z",
  "modified_at": null
}
```

This endpoint creates a season.

### HTTP Request

`POST https://turnej.com/api/seasons`

### Body Parameters

| Parameter  | Type   | Description                  |
| ---------- | ------ | ---------------------------- |
| name       | String | The full name of the season. |
| event_date | Date   | The date of the event.       |
| location   | String | The name of the location.    |

### Returned Values

| Parameter   | Type       | Description                                                                          |
| ----------- | ---------- | ------------------------------------------------------------------------------------ |
| id          | Integer    | The unique id of the season.                                                         |
| status      | StatusType | The status of the season.                                                            |
| name        | String     | The full name of the season.                                                         |
| event_date  | Date       | The date of the event.                                                               |
| location    | String     | The name of the location.                                                            |
| completed   | Boolean    | If true the season is completed. This means that all games have been also completed. |
| locked      | Boolean    | If the season is locked, then no changes can be made to it.                          |
| version     | Integer    | How many times the season has been changed.                                          |
| created_at  | Date       | The date when the season was created.                                                |
| modified_at | Date       | The date when the season was modified.                                               |

## PATCH: Create a Season

```shell
curl 'https://turnej.com/api/seasons'
  -X PATCH
  -H 'Content-Type: application/json'
  -d '{"name": "Season 2", "location": "Some other location", "event_date": "DATE", "completed": true, "locked": true}'
```

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "status": "ACTIVE",
  "name": "Season 2",
  "event_date": "1970-01-19T08:56:37.337Z",
  "location": "Some other location",
  "completed": true,
  "locked": true,
  "version": 1,
  "created_at": "2020-04-20T15:42:17.058Z",
  "modified_at": "2020-04-20T15:42:17.058Z"
}
```

This endpoint updates a season.

### HTTP Request

`POST https://turnej.com/api/seasons/<ID>`

### URL Parameters

| Parameter | Description                    |
| --------- | ------------------------------ |
| ID        | The ID of the season to delete |

### Body Parameters

| Parameter  | Type    | Description                                                                          |
| ---------- | ------- | ------------------------------------------------------------------------------------ |
| name       | String  | The full name of the season.                                                         |
| event_date | Date    | The date of the event.                                                               |
| location   | String  | The name of the location.                                                            |
| completed  | Boolean | If true the season is completed. This means that all games have been also completed. |
| locked     | Boolean | If the season is locked, then no changes can be made to it.                          |

### Returned Values

| Parameter   | Type       | Description                                                                          |
| ----------- | ---------- | ------------------------------------------------------------------------------------ |
| id          | Integer    | The unique id of the season.                                                         |
| status      | StatusType | The status of the season.                                                            |
| name        | String     | The full name of the season.                                                         |
| event_date  | Date       | The date of the event.                                                               |
| location    | String     | The name of the location.                                                            |
| completed   | Boolean    | If true the season is completed. This means that all games have been also completed. |
| locked      | Boolean    | If the season is locked, then no changes can be made to it.                          |
| version     | Integer    | How many times the season has been changed.                                          |
| created_at  | Date       | The date when the season was created.                                                |
| modified_at | Date       | The date when the season was modified.                                               |

## DELTETE: Specific Season

```shell
curl 'https://turnej.com/api/seasons/1'
  -X DELETE
```

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "status": "DELETED",
  "name": "Season 1",
  "event_date": "1970-01-19T08:56:37.337Z",
  "location": "Some location",
  "completed": false,
  "locked": false,
  "version": 0,
  "created_at": "2020-04-20T15:42:17.058Z",
  "modified_at": ""
}
```

This endpoint does deletes a season.  
It does not delete it from the database. It only sets the status of the season to 'DELETED'.

### HTTP Request

`DELETE https://turnej.com/seasons/<ID>`

### URL Parameters

| Parameter | Description                    |
| --------- | ------------------------------ |
| ID        | The ID of the season to delete |

### Returned Values

| Parameter   | Type       | Description                                                                          |
| ----------- | ---------- | ------------------------------------------------------------------------------------ |
| id          | Integer    | The unique id of the season.                                                         |
| status      | StatusType | The status of the season.                                                            |
| name        | String     | The full name of the season.                                                         |
| event_date  | Date       | The date of the event.                                                               |
| location    | String     | The name of the location.                                                            |
| completed   | Boolean    | If true the season is completed. This means that all games have been also completed. |
| locked      | Boolean    | If the season is locked, then no changes can be made to it.                          |
| version     | Integer    | How many times the season has been changed.                                          |
| created_at  | Date       | The date when the season was created.                                                |
| modified_at | Date       | The date when the season was modified.                                               |
