# User API Spec

## Register User

Endpoint: POST /api/users

Request Body:

```json
{
  "username": "harundarat",
  "password": "rahasai",
  "name": "Harun Al Rasyid"
}
```

Response Body (Success):

```json
{
  "data": {
    "username": "harundarat",
    "name": "Harun Al Rasyid"
  }
}
```

Response Body (Failed):

```json
	"errors" : "Username must not blank!"
```

## Login User

Endpoint: POST /api/users/login

Request Body:

```json
{
  "username": "harundarat",
  "password": "rahasai"
}
```

Response Body (Success):

```json
{
  "data": {
    "username": "harundarat",
    "name": "Harun Al Rasyid",
    "token": "uuid"
  }
}
```

Response Body (Failed):

```json
	"errors" : "Username or password wrong!"
```

## Get User

Endpoint: GET /api/users/current

Request Header:

- X-API-TOKEN : token

Response Body (Success):

```json
{
  "data": {
    "username": "harundarat",
    "name": "Harun Al Rasyid"
  }
}
```

Response Body (Failed):

```json
	"errors" : "Unauthorized, ..."
```

## Update User

Endpoint: PATCH /api/users/current

Request Header:

- X-API-TOKEN : token

Request Body:

```json
{
  "password": "rahasai", //optional
  "name": "Harun Al Rasyid" //optional
}
```

Response Body (Success):

```json
{
  "data": {
    "username": "harundarat",
    "name": "Harun Al Rasyid"
  }
}
```

Response Body (Failed):

```json
	"errors" : "Unauthorized, ..."
```

## Logout User

Endpoint: DELETE /api/users/current

Request Header:

- X-API-TOKEN : token

Request Body:

Response Body (Success):

```json
{
  "data": "OK"
}
```

Response Body (Failed):

```json
	"errors" : "Unauthorized, ..."
```
