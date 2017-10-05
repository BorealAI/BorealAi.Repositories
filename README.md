# Boreal.AI API

## Overview

Boreal.AI provides a REST API for managing responses for chat bots and voice assistants. 

How does that work? Rather than hardcoding pre-defined answers developers indicate what response intent they logic arrived at, hit the api.boreal.ai endpoint and receive textual representation of that intent. Our backend will take care or making sure, there's variability in the responses.

For instance, a chatbot wants to greet a user. Just hit the api.boreal.ai with GREET.USER intent and display received utterance.  

And the best part? Boreal.AI uses some smart AI and algos to learn and improve the range of responses over time.

To get started sign up at www.boreal.ai with a Facebook account. Two free subscriptions will be provided.

## AUTHENTICATION

Boreal.AI API uses API Key based authentication - with two types of API KEYS:
- Each subscription can have one or more read-only API keys, which supposed to be used for regular interactions, like querying for intent responses.
- Each subscription will have one master API KEY, which should be used to update subscription details (like adding / removing / changing read-only API KEYs), Creating or updating intent repositories.

The required value should be passed via api_key argument.

## Requests

```
{
  "intentName": "greet.user",
  "entities": [
    {
      "entityName": "user_name",
      "entityValue": "Bob"
    }
  ],
  "contextData": [
    {
      "ContextName": "style",
      "ContextValue": "casual",
      "IsOptional": true
    }
  ],
  "allowOffTopicResponses": true
}
```

## Responses

A response can contain one or more lines of text as below.

```
{
  "textResponses": [
    "Howdy Bob"
  ]
}
```

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

TODO

### List repositories in a subscription

TODO

### Update an existing intent repository

TODO

### List intentns in repository 

TODO

## Intent Utterance Markdown Syntax

TODO

### Variants:

TODO

### Entities:

TODO

### Optionals

TODO
