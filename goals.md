# PLUGIN GOALS

## CREATE BRAND NEW GOALS

### Method: POST

#### Description

 This endpoint creates a new goals for a particular organization.

#### Parameters

org_id of String datatype query is to be Provided to create a new goal.
  
  ```sh
org_id=6145d099285e4a184020742e
  ```

#### Request body

- Application/JSON

Provide the required field to create a new goal

```sh
{
  "category": "#backend",
  "description": "test goal",
  "start_date": "2020-10-02",
  "due_date": "2020-10-02",
  "goal_type": "annual",
  "goal_name": "public room"
}
```

#### Responses

```sh
curl -X 'POST' \
  'https://goals.zuri.chat/api/v1/goals?org_id=6145d099285e4a184020742e' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{
  "category": "#backend",
  "description": "test goal",
  "start_date": "2020-10-02",
  "due_date": "2020-10-02",
  "goal_type": "annual",
  "goal_name": "public room"
}'
```

#### Request URL

```sh
https://goals.zuri.chat/api/v1/goals?org_id=6145d099285e4a184020742e

```

### Server Responses

#### Code: 200

 Descripton: Success

- response body

```sh
{
  "message": "success",
  "status": 200,
  "data": {
    "room_id": "8d9273ef-76c7-4a6d-a4b5-d8e4fad2e60f",
    "isComplete": false,
    "isExpired": false,
    "category": "#backend",
    "description": "test goal",
    "start_date": "2020-10-02",
    "due_date": "2020-10-02",
    "goal_type": "annual",
    "goal_name": "public room"
  }
}
```

- Response headers

```sh
 access-control-allow-origin: * 
 connection: keep-alive 
 content-length: 274 
 content-type: application/json; charset=utf-8 
 date: Thu,23 Sep 2021 23:19:47 GMT 
 etag: W/"112-mV/fElo6poaST4+3EJoR2J/HmdA" 
 server: nginx/1.18.0 (Ubuntu) 
 vary: Origin,Accept-Encoding 
 x-powered-by: Express 
```

#### Code 400

Description: Bad request

- Response body

```sh
{
  "error": "Goal with the title: 'public room' and  category: '#backend' already exists on your organization"
}
```

- Response headers

```sh
 connection: keep-alive 
 content-length: 108 
 content-type: application/json; charset=utf-8 
 date: Thu,23 Sep 2021 23:32:03 GMT 
 etag: W/"6c-kjuKkL4MGQb2go/b8Whj5p2ztug" 
 server: nginx/1.18.0 (Ubuntu) 
 vary: Origin,Accept-Encoding 
 x-powered-by: Express 
```

#### Code 401

Description: Unauthorized

#### Code 404

Description: Not found

#### Code 500

Description: Internal service error.

## UPDATE A SINGLE GOAL

### METHOD: PUT

#### Description

This endpoint updates a single goal for a particular organization.

#### Parameters

- org_id: Provide an org_id of string datatype to fetch a single goal.

```sh
  "_id": "613ddbd3e4010959c8dc0c5e"
```

- room_id: Provide a room_id to fetch a single goal.

```sh
   "room_id": "b66e5fe5-2c66-413c-b2fc-a38d6ab76330"
```

### RESPONSES

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

#### SERVER RESPONSE

##### CODE 200

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

##### CODE 400

Description: Bad Request

##### CODE 401

Description: Unauthorized

##### CODE 404

Description: Error: Not Found

###### Response body

```sh
{
  "status": "fail",
  "message": "Can't find /api/v1/goals/update on this server!"
}
```

###### Response Headers

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

##### CODE 500

Description: Internal Service Error.

## DELETE A SINGLE GOAL

### METHOD: DELETE

#### Description

This endpoint delete a single goal for a particular organization.

#### Parameters

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

#### Responses

##### curl

```sh
curl -X 'DELETE' \
  'https://goals.zuri.chat/api/v1/goals/delete?org_id=200&goal_id=613fa4a56173056af01b4b26' \
  -H 'accept: application/json'
```

##### Request URL

```sh
https://goals.zuri.chat/api/v1/goals/delete?org_id=200&goal_id=613fa4a56173056af01b4b26
```

##### Server Response

###### CODE 200

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

###### CODE 400

Description: Bad Request

##### CODE 401

Description: Unauthorized

##### CODE 404

Description: Error Not found

###### Response body

```sh
{
  "error": "There is no goal of this id attached to this organization id that was found."
}
```

###### Response Headers

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

##### CODE 500

Description: Internal Server Error.
