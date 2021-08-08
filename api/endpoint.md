---
description: A list of all currently available and usable endpoints or features.
---

# Endpoint

## Game

Game-related endpoint category.

{% api-method method="get" host="https://api.sdev.web.id" path="/game/list" %}
{% api-method-summary %}
Game List
{% endapi-method-summary %}

{% api-method-description %}
Get a list of available games and servers along with their active status.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Bearer &lt;API KEY&gt;
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
The response you will receive if the request is successful.
{% endapi-method-response-example-description %}

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
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
A response will be returned if the data to be submitted is incomplete.
{% endapi-method-response-example-description %}

```javascript
{
  "code": 400,
  "status": false,
  "messages": "Incoming request body doesn't contain a valid data."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
The response you will get if the API KEY you are using is not/not yet valid.
{% endapi-method-response-example-description %}

```javascript
{
  "code": 401,
  "status": false,
  "messages": "Unknown API key. Please check your API key and try again."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}
The following is response you will receive if the API KEY you are using is being suspended.
{% endapi-method-response-example-description %}

```javascript
{
  "code": 403,
  "status": false,
  "messages": "Your account has been temporarily suspended."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=429 %}
{% api-method-response-example-description %}
The response that will be returned if the API KEY used has exceeded the daily usage limit.
{% endapi-method-response-example-description %}

```javascript
{
  "code": 429,
  "status": false,
  "messages": "Request for your API key has exceeded the usage limit."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}
The response you will be receive if something goes wrong on the client or server side. Please contact the administrator immediately if you get a response like the following.
{% endapi-method-response-example-description %}

```javascript
{
  "code": 500,
  "status": false,
  "messages": "An error occurred either from the client or server.",
  "errors": "..."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.sdev.web.id" path="/game/id" %}
{% api-method-summary %}
Game ID Checker
{% endapi-method-summary %}

{% api-method-description %}
Retrieve nickname and availability of online game accounts based on user id.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Bearer &lt;APIKEY&gt;
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="game" type="number" required=true %}
Game ID from our list to check
{% endapi-method-parameter %}

{% api-method-parameter name="id" type="string" required=true %}
User ID of account that must be checked
{% endapi-method-parameter %}

{% api-method-parameter name="server" type="string" required=false %}
Game server code/ID from our list
{% endapi-method-parameter %}

{% api-method-parameter name="role" type="string" required=false %}
Game account role \(only for specific game\)
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
The response you will receive if the request is successful.
{% endapi-method-response-example-description %}

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
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

