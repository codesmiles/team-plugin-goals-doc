# CREATE BRAND NEW GOALS

## Method: POST

### Description

 This endpoint creates a new goals for a particular organization.

### Parameters

org_id of String datatype query is to be Provided to create a new goal.
  
  ```sh
org_id=6145d099285e4a184020742e
  ```

### Request body

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

### Responses

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

### Request URL

```sh
https://goals.zuri.chat/api/v1/goals?org_id=6145d099285e4a184020742e

```

## Server Responses

### Code: 200

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

### Code 400

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

### Code 401

Description: Unauthorized

### Code 404

Description: Not found

### Code 500

Description: Internal service error.
