# Boreal.AI API

## Overview

To get started register at www.boreal.ai with a Facebook account. Two free subscriptions will be provided.

## AUTHENTICATION

Boreal.AI API uses API Key based authentication - with two types of API KEYS:
- Each subscription can have one or more read-only API keys, which supposed to be used for regular interactions, like querying for intent responses.
- Each subscription will have one master API KEY, which should be used to update subscription details (like adding / removing / changing read-only API KEYs), Creating or updating intent repositories.

The required value should be passed via api_key argument.

## Requests

## Responses

The Boreal.AI API uses the standard HTTP status codes to indicate the result of a request. All responses are in JSON form.

###Error responses

Erro responses include textual information of what when wrong as well as an enumeration describing error type.:

```
{
    "error": "error_type_enum",
    "description": "textual description of the error"
}
```

## ENDPOINT

The base url for all API requests is:
```
https://api.boreal.ai/
```


You can also check the swagger UI
```
https://api.boreal.ai/swagger
```

### Create new intent repository

### List repositories in a subscription

### Update an existing intent repository

### List intentns in repository 

## Intent Utterance Markdown Syntax

### Variants:

### Entities:

### Optionals
