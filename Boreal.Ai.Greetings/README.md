# Boreal.Ai.Greetings repository
This is a demo repository with some generic response intents, including:
"greet.user"

BorealAi REST api can be accessed via: https://api.boreal.ai/swagger

Access to demo subscription and repository:
   
    subscriptionId: d492ea2b-12e7-4a30-9dfc-86c75ae53daa
    apiKey: bb58063f-43cc-475b-a269-d1f24ea59ed4 (READER-Access only)

# Getting list of registered intents & entities:
```
curl -X GET --header 'Accept: application/json' 'https://api.boreal.ai/api/subscriptions/d492ea2b-12e7-4a30-9dfc-86c75ae53daa/repositories/9a691ef5-e822-4468-ae1b-e65bcd9c9779?api_key=bb58063f-43cc-475b-a269-d1f24ea59ed4'
```
or
```
GET: https://api.boreal.ai/api/subscriptions/d492ea2b-12e7-4a30-9dfc-86c75ae53daa/repositories/9a691ef5-e822-4468-ae1b-e65bcd9c9779?api_key=bb58063f-43cc-475b-a269-d1f24ea59ed4
```
Response:
```
{
  "id": "9a691ef5-e822-4468-ae1b-e65bcd9c9779",
  "intents": [
    {
      "intentName": "greet.user",
      "intentEntities": []
    },
    {
      "intentName": "greet.user",
      "intentEntities": [
        "username"
      ]
    }
  ],
  "currentRepositorySourceRefLink": {
    "version": 5,
    "url": "api/subscriptions/d492ea2b-12e7-4a30-9dfc-86c75ae53daa/repositories/9a691ef5-e822-4468-ae1b-e65bcd9c9779/sources/5"
  }
}
```

# Retrieving utterance for an intent
```
curl -X POST --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{"intentName": "greet.user"}' 'https://api.boreal.ai/api/subscriptions/d492ea2b-12e7-4a30-9dfc-86c75ae53daa/responses/user112345?api_key=bb58063f-43cc-475b-a269-d1f24ea59ed4'
```
or
```
POST: https://api.boreal.ai/api/subscriptions/d492ea2b-12e7-4a30-9dfc-86c75ae53daa/responses/user112345?api_key=bb58063f-43cc-475b-a269-d1f24ea59ed4
```
Payload:
```
{"intentName": "greet.user"}
```
# Retrieving utterance for intent with entity
(e.g. we want to green user who's name is Bob)
```
curl -X POST --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{ \ 
 "intentName": "greet.user", \ 
 "entities": [ \ 
 { \ 
 "entityName": "username", \ 
 "entityValue": "Bob" \ 
 }]}' 'https://api.boreal.ai/api/subscriptions/d492ea2b-12e7-4a30-9dfc-86c75ae53daa/responses/user112345?api_key=bb58063f-43cc-475b-a269-d1f24ea59ed4'
```
 or
```
POST: https://api.boreal.ai/api/subscriptions/d492ea2b-12e7-4a30-9dfc-86c75ae53daa/responses/user112345?api_key=bb58063f-43cc-475b-a269-d1f24ea59ed4
```
Payload
```
{
  "intentName": "greet.user",
  "entities": [
    {
      "entityName": "username",
      "entityValue": "Bob"
    }
  ]
}
```
