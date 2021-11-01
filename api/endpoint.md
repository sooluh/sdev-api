---
description: A list of all currently available and usable endpoints or features.
---

# 🔥 Endpoint

## Game

Game-related endpoint category.

{% swagger baseUrl="https://api.sdev.web.id" path="/game/list" method="get" summary="Game List" %}
{% swagger-description %}
Get a list of available games and servers along with their active status.
{% endswagger-description %}

{% swagger-parameter name="Authorization" type="string" required="true" in="header" %}
Bearer <API KEY>
{% endswagger-parameter %}

{% swagger-response status="200" description="The response you will receive if the request is successful." %}
```javascript
{
  "code": 200,
  "status": true,
  "messages": "Data was successfully parsed, please use data as needed.",
  "data": [
    ...
    {
      "name": "RAGNAROK MOBILE",
      "id": "104",
      "servers": {
        "901": "Eternal Love",
        "902": "Midnight Party",
        "903": "Memory of Faith"
      },
      "status": "active"
    },
    ...
    {
      "name": "BLEACH MOBILE 3D",
      "id": "110",
      "servers": {},
      "status": "inactive"
    }
    ...
  ]
}
```
{% endswagger-response %}

{% swagger-response status="400" description="A response will be returned if the data to be submitted is incomplete." %}
```javascript
{
  "code": 400,
  "status": false,
  "messages": "Incoming request body doesn't contain a valid data."
}
```
{% endswagger-response %}

{% swagger-response status="401" description="The response you will get if the API KEY you are using is not/not yet valid." %}
```javascript
{
  "code": 401,
  "status": false,
  "messages": "Unknown API key. Please check your API key and try again."
}
```
{% endswagger-response %}

{% swagger-response status="403" description="The following is response you will receive if the API KEY you are using is being suspended." %}
```javascript
{
  "code": 403,
  "status": false,
  "messages": "Your account has been temporarily suspended."
}
```
{% endswagger-response %}

{% swagger-response status="429" description="The response that will be returned if the API KEY used has exceeded the daily usage limit." %}
```javascript
{
  "code": 429,
  "status": false,
  "messages": "Request for your API key has exceeded the usage limit."
}
```
{% endswagger-response %}

{% swagger-response status="500" description="The response you will be receive if something goes wrong on the client or server side. Please contact the administrator immediately if you get a response like the following." %}
```javascript
{
  "code": 500,
  "status": false,
  "messages": "An error occurred either from the client or server.",
  "errors": "..."
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="https://api.sdev.web.id" path="/game/id" method="get" summary="Game ID Checker" %}
{% swagger-description %}
Retrieve nickname and availability of online game accounts based on user id.
{% endswagger-description %}

{% swagger-parameter name="Authorization" type="string" required="true" in="header" %}
Bearer <APIKEY>
{% endswagger-parameter %}

{% swagger-parameter name="game" type="number" required="true" in="query" %}
Game ID from our list to check
{% endswagger-parameter %}

{% swagger-parameter name="id" type="string" required="true" in="query" %}
User ID of account that must be checked
{% endswagger-parameter %}

{% swagger-parameter name="server" type="string" required="false" in="query" %}
Game server code/ID from our list
{% endswagger-parameter %}

{% swagger-parameter name="role" type="string" required="false" in="query" %}
Game account role (only for specific game)
{% endswagger-parameter %}

{% swagger-response status="200" description="The response you will receive if the request is successful." %}
```javascript
{
  "code": 200,
  "status": true,
  "messages": "Data was successfully parsed, please use data as needed.",
  "data": {
    "exist": true,
    "nick": "..."
  }
}
```
{% endswagger-response %}
{% endswagger %}
