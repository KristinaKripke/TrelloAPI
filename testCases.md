Trello API https://developer.atlassian.com/cloud/trello/rest/api-group-actions/#api-group-actions
   
### TS 1. Create a board:   

#### TC 1.1. Create board with valid query params.      
1. HTTP method: POST    
2. Endpoint: /boards/  
3. Query params: name=string, key, token

***Expected response:***
1. Response code 200
2. Response time below 800ms
3. Response body: check attached 
[newBoardResponseBody.json](/responseBodies/newBoardResponseBody.json)

#### TC 1.2. Create board without query params
1. HTTP method: POST
2. Endpoint: /boards/
3. Query params: no params

***Expected response:*** 
1. Response code 400
2. Response time below 800ms
3. Response body:
    {
        "message": "invalid value for name",
        "error": "ERROR"
    }

#### TC 1.3. Create board without token
1. HTTP method: POST 
2. Endpoint: /boards/
3. Query params: name=string, key

***Expected response:***
1. Response code 401
2. Response time below 800ms
3. Response body: 
    {
        "message": "missing scopes"
    }

#### TC 1.4. Create board without key
1. HTTP method: POST 
2. Endpoint: /boards/
3. Query params: name=string, token

***Expected response:***
1. Response code 401
2. Response time below 800ms
3. Response body: invalid key

#### TC 1.5. Create board without name
1. HTTP method: POST 
2. Endpoint: /boards/
3. Query params: key, token

***Expected response:***
1. Response code 400
2. Response time below 800ms
3. Response body:
    {
        "message": "invalid value for name",
        "error": "ERROR"
    }

### TS 2. Get boards:

#### TC 2.1. Get all boards
1. HTTP method: GET
2. Endpoint: /members/me/boards
3. Query params: key, token 

***Expected response:***
1. Response code 200
2. Response time below 800ms
3. Response body: array of boards to not be empty

#### TC 2.2. Get one board
1. HTTP method GET 
2. Endpoint: /boards/:id
3. Query params: key, token
4. Path params: board id

***Expected response:*** 
1. Response code 200
2. Response time below 800ms
3. Response body: [boardResponseBody.json](/responseBodies/boardResponseBody.json)

#### TC 2.3 Get board without token
1. HTTP method GET 
2. Endpoint: /boards/:id
3. Query params: key
4. Path params: board id

***Expected response:*** 
1. Response code 401
2. Response time below 800ms
3. Response body: 
{
    "message": "missing scopes"
}

#### TC 2.4 Get board without key
1. HTTP method GET 
2. Endpoint: /boards/:id
3. Query params: token
4. Path params: board id

***Expected response:*** 
1. Response code 401
2. Response time below 800ms
3. Response body: invalid key

#### TC 2.5 Get board without board id
1. HTTP method GET 
2. Endpoint: /boards/:id
3. Query params: token, key
4. Path params: no params

***Expected response:*** 
1. Response code 400
2. Response time below 800ms
3. Response body: invalid id

### TS 3. Update Board

#### TC 3.1 Update board name 
1. HTTP method PUT
2. Endpoint: /boards/:id
3. Query params: token, key, name, labelNames/red
4. Path params: board id

***Expected response:*** 
1. Response code 200
2. Response time below 800ms
3. Response body: [updatedBoardResponseBody.json](/responseBodies/updatedBoardResponseBody.json)

#### TC 3.2 Update board without token
1. HTTP method PUT
2. Endpoint: /boards/:id
3. Query params: key, name, labelNames/red
4. Path params: board id

***Expected response:*** 
1. Response code 401
2. Response time below 800ms
3. Response body: 
{
    "message": "missing scopes"
}

#### TC 3.3 Update board without key
1. HTTP method PUT
2. Endpoint: /boards/:id
3. Query params: token, name, labelNames/red
4. Path params: board id

***Expected response:*** 
1. Response code 401
2. Response time below 800ms
3. Response body: invalid key

#### TC 3.4 Update board without board id
1. HTTP method PUT
2. Endpoint: /boards/:id
3. Query params: token, name, labelNames/red
4. Path params: no params

***Expected response:*** 
1. Response code 400
2. Response time below 800ms
3. Response body: invalid id

### TS 4. Delete board

#### TC 4.1 Delete board
1. HTTP method DELETE
2. Endpoint: /boards/:id
3. Query params: token, key
4. Path params: id

***Expected response:*** 
1. Response code 200
2. Response time below 800ms
3. Response body:
{
    "_value": null
}

#### TC 4.2 Delete board without auth
1. HTTP method DELETE
2. Endpoint: /boards/:id
3. Query params: no params
4. Path params: id

***Expected response:*** 
1. Response code 401
2. Response time below 800ms
3. Response body: 
{
    "message": "missing scopes"
}

#### TC 4.3 Delete board without id
1. HTTP method DELETE
2. Endpoint: /boards/:id
3. Query params: token, key
4. Path params: no params

***Expected response:*** 
1. Response code 400
2. Response time below 800ms
3. Response body: invalid id

#### TC 4.4 Get deleted board
1. HTTP method GET
2. Endpoint: /boards/:id
3. Query params: token, key
4. Path params: id

***Expected response:*** 
1. Response code 404
2. Response time below 800ms
3. Response body: The requested resource was not found.

### TS 5. Create a list

#### TC 5.1 Create a list
1. HTTP method POST
2. Endpoint: /lists
3. Query params: key, token, name, idBoard

***Expected response:*** 
1. Response code 200
2. Response time below 800ms
3. Response body: [createListResponseBody](/responseBodies/createListResposneBody.json)

#### TC 5.2 Create a list without token
1. HTTP method POST
2. Endpoint: /lists
3. Query params: key, name, idBoard

***Expected response:*** 
1. Response code 401
2. Response time below 800ms
3. Response body: 
{
    "message": "missing scopes"
}

#### TC 5.3 Create a list without key
1. HTTP method POST
2. Endpoint: /lists
3. Query params: token, name, idBoard

***Expected response:*** 
1. Response code 401
2. Response time below 800ms
3. Response body: invalid key

#### TC 5.4 Create a list without name
1. HTTP method POST
2. Endpoint: /lists
3. Query params: token, key, idBoard

***Expected response:*** 
1. Response code 400
2. Response time below 800ms
3. Response body: invalid value for name

#### TC 5.5 Create a list without board id
1. HTTP method POST
2. Endpoint: /lists
3. Query params: token, key, name

***Expected response:*** 
1. Response code 400
2. Response time below 800ms
3. Response body: invalid value for idBoard

### TS 6. Get a list 

#### TC 6.1 Get a list
1. HTTP method GET
2. Endpoint: /lists/:id
3. Query params: token, key
4. Path params: id

***Expected response:*** 
1. Response code 200
2. Response time below 800ms
3. Response body: [getListResponseBody](/responseBodies/getListResponseBody.json)

#### TC 6.2 Get a list without auth
1. HTTP method GET
2. Endpoint: /lists/:id
3. Query params: no params
4. Path params: id

***Expected response:*** 
1. Response code 401
2. Response time below 800ms
3. Response body: unauthorized permission requested

#### TC 6.3 Get a list without list id
1. HTTP method GET
2. Endpoint: /lists
3. Query params: token, key
4. Path params: no params

***Expected response:*** 
1. Response code 400
2. Response time below 800ms
3. Response body: invalid id

### TS 7. Move list to a board

#### TC 7.1 Move list to a board
1. HTTP method PUT
2. Endpoint: /lists/:id/idBoard
3. Query params: token, key, value
4. Path params: list id

***Expected response:*** 
1. Response code 200
2. Response time below 800ms
3. Response body: [moveListToBoardResponseBody](/responseBodies/moveListToBoardResponseBody.json)


#### TC 7.2 Move list to a board without auth
1. HTTP method PUT
2. Endpoint: /lists/:id/idBoard
3. Query params: value
4. Path params: list id

***Expected response:*** 
1. Response code 401
2. Response time below 800ms
3. Response body: 
{
    "message": "missing scopes"
}

#### TC 7.3 Move list to a board without idBoard
1. HTTP method PUT
2. Endpoint: /lists/:id/idBoard
3. Query params: key, token
4. Path params: list id

***Expected response:*** 
1. Response code 400
2. Response time below 800ms
3. Response body:
{
    "message": "invalid id",
    "error": "BAD_REQUEST_ERROR"
}

#### TC 7.4 Move list to a board without list id
1. HTTP method PUT
2. Endpoint: /lists/:id/idBoard
3. Query params: key, token, value
4. Path params: no params

***Expected response:*** 
1. Response code 400
2. Response time below 800ms
3. Response body: invalid id

### TS 8. Create a card

#### TC 8.1 Create a card
1. HTTP method POST
2. Endpoint: /cards
3. Query params: key, token, idList

***Expected response:*** 
1. Response code 200
2. Response time below 800ms
3. Response body: [createCardResponseBody.json](/responseBodies/createCardResponseBody.json)

#### TC 8.2 Create a card without auth
1. HTTP method POST
2. Endpoint: /cards
3. Query params: idList

***Expected response:*** 
1. Response code 401
2. Response time below 800ms
3. Response body:
{
    "message": "missing scopes"
}

#### TC 8.3 Create a card without list id
1. HTTP method POST
2. Endpoint: /cards
3. Query params: key, token

***Expected response:*** 
1. Response code 400
2. Response time below 800ms
3. Response body: invalid value for idList

### TS 9. Get a card

#### TC 9.1 Get a card
1. HTTP method GET
2. Endpoint: /cards/:id
3. Query params: key, token
4. Path params: id

***Expected response:*** 
1. Response code 200
2. Response time below 800ms
3. Response body: [getCardResponseBody.json](/responseBodies/getCardResponseBody.json)

#### TC 9.2 Get a card without auth
1. HTTP method GET
2. Endpoint: /cards/:id
3. Query params: no params
4. Path params: id

***Expected response:*** 
1. Response code 401
2. Response time below 800ms
3. Response body: unauthorized card permission requested

#### TC 9.3 Get a card without card id
1. HTTP method GET
2. Endpoint: /cards/:id
3. Query params: token, key
4. Path params: no params

***Expected response:*** 
1. Response code 400
2. Response time below 800ms
3. Response body: invalid id

### TS 10. Delete card

#### TC 10.1 Delete card
1. HTTP method DELETE
2. Endpoint: /cards/:id
3. Query params: token, key
4. Path params: id

***Expected response:*** 
1. Response code 200
2. Response time below 800ms
3. Response body: 
{
    "limits": {}
}

#### TC 10.2 Delete card without auth
1. HTTP method DELETE
2. Endpoint: /cards/:id
3. Query params: no params
4. Path params: id

***Expected response:*** 
1. Response code 401
2. Response time below 800ms
3. Response body: 
{
    "message": "missing scopes"
}

#### TC 10.3 Delete card without id
1. HTTP method DELETE
2. Endpoint: /cards/:id
3. Query params: key, token
4. Path params: no params

***Expected response:*** 
1. Response code: 400
2. Response time below 800ms
3. Response body: invalid id

#### TC 10.4 Delete card that is already deleted
1. HTTP method DELETE
2. Endpoint: /cards/:id
3. Query params: key, token
4. Path params: id

***Expected response:*** 
1. Response code: 404
2. Response time below 800ms
3. Response body: The requested resource was not found.

#### TC 10.5 Get card that is already deleted
1. HTTP method GET
2. Endpoint: /cards/:id
3. Query params: key, token
4. Path params: id

***Expected response:*** 
1. Response code: 404
2. Response time below 800ms
3. Response body: The requested resource was not found.

