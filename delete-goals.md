# DELETE A SINGLE GOAL

## METHOD: DELETE

### Description

This endpoint delete a single goal for a particular organization.

### Parameters

- org_id: Provide an org_id of string datatype as a query to delete a single goal.
example:

```sh
200
```

- goal_id: Provide a goal_id og string datatype as a query to delete a single goal.
example:

```sh
 613fa4a56173056af01b4b26
```

## Responses

### curl

```sh
curl -X 'DELETE' \
  'https://goals.zuri.chat/api/v1/goals/delete?org_id=200&goal_id=613fa4a56173056af01b4b26' \
  -H 'accept: application/json'
```

### Request URL

```sh
https://goals.zuri.chat/api/v1/goals/delete?org_id=200&goal_id=613fa4a56173056af01b4b26
```

### Server Response

#### CODE 200

- Description: success
- Media type: application/JSON

Example

```sh
{
  "status": "200",
  "message": "success",
  "data": [
    {
      "_id": "613ddbd3e4010959c8dc0c5e",
      "category": "#backend",
      "createdBy": "Depeju",
      "description": "test goal",
      "start_date": "2020-10-02",
      "due_date": "2020-10-02",
      "goal_type": "annual",
      "goal_name": "public room",
      "isComplete": true,
      "isExpired": true,
      "room_id": "b66e5fe5-2c66-413c-b2fc-a38d6ab76330"
    }
  ]
}
```

#### CODE 400

Description: Bad Request

#### CODE 401

Description: Unauthorized

#### CODE 404

Description: Error Not found

##### Response body

```sh
{
  "error": "There is no goal of this id attached to this organization id that was found."
}
```

##### Response Headers

```sh
 connection: keep-alive 
 content-length: 88 
 content-type: application/json; charset=utf-8 
 date: Fri,24 Sep 2021 11:55:45 GMT 
 etag: W/"58-O4mzMWV8a2dIAxBxaYRFM3ctKxo" 
 server: nginx/1.18.0 (Ubuntu) 
 vary: Origin,Accept-Encoding 
 x-powered-by: Express 
```

#### CODE 500

Description: Internal Server Error.
