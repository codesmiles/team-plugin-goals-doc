# UPDATE A SINGLE GOAL

## METHOD: PUT

### Description

This endpoint updates a single goal for a particular organization.

### Parameters

- org_id: Provide an org_id of string datatype to fetch a single goal.

```sh
  "_id": "613ddbd3e4010959c8dc0c5e"
```

- room_id: Provide a room_id to fetch a single goal.

```sh
   "room_id": "b66e5fe5-2c66-413c-b2fc-a38d6ab76330"
```

## RESPONSES

- curl

```sh
curl -X 'PUT' \
  'https://goals.zuri.chat/api/v1/goals/update' \
  -H 'accept: application/json'
```

- Request URL

```sh
https://goals.zuri.chat/api/v1/goals/update
```

### SERVER RESPONSE

#### CODE 200

- Descripton: Success

- Media type: Application.JSON

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

Description: Error: Not Found

##### Response body

```sh
{
  "status": "fail",
  "message": "Can't find /api/v1/goals/update on this server!"
}
```

##### Response Headers

```sh
 connection: keep-alive 
 content-length: 77 
 content-type: application/json; charset=utf-8 
 date: Fri,24 Sep 2021 10:27:34 GMT 
 etag: W/"4d-DxnsFFxghCfWE9M6XOpiCeb/UlM" 
 server: nginx/1.18.0 (Ubuntu) 
 vary: Origin,Accept-Encoding 
 x-powered-by: Express 
```

#### CODE 500

Description: Internal Service Error.
