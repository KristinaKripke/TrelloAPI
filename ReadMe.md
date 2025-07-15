# Trello API
![picture](/Blog-API.webp)
### API testing project

### 🌟 About
This project serves as an educational resource to test REST APIs using Postman, newman, and Node.js. It provides practical, hands-on experience with automating API tests, validating responses, and integrating tests into CI/CD workflows, running tests automatically with GitHub Actions. Test scenarios for this projects:   
1. Create a board.     
2. Get boards.       
3. Update board.      
4. Delete board.     
5. Create a list.       
6. Get a list.     
7. Move list to another board.      
8. Create a card.      
9. Get a card.       
10. Delete a card.         

There are positive and negative test cases for all scenarios. A total of 129 tests. If everything is set up correctly all tests are passing.
You can find all test cases here: [Test cases](/testCases.md)

***API documentation:*** [TrelloAPI](https://developer.atlassian.com/cloud/trello/rest/api-group-actions/#api-group-actions)

### 🎯 Project features/goals:  
Postman  
Postman scripts   
newman
GitHub actions  

### 💻 Prerequisites:  
Node.js  
newman 

### 🏃 Installation:  
Would like to run this project locally? Open terminal and follow these steps:

1. Clone the repo

```git clone https://github.com/KristinaKripke/TrelloAPI ```

2. Install NPM packages

```npm install```

3. Install newman

```npm install newman```

4. Get token and key for Trello authorization    

[Get Trello authorization here](https://developer.atlassian.com/cloud/trello/power-ups/rest-api-client/#client-initialization)

5. Add environment file env.json (to run locally).    

```
{
	"id": "123 or YOUR_POSTMAN_ID",
	"name": "TrelloEnv",
	"values": [
		{
			"key": "key",
			"value": "YOUR_KEY",
			"type": "default",
			"enabled": true
		},
		{
			"key": "token",
			"value": "YOUR_TOKEN",
			"type": "default",
			"enabled": true
		}
	],
	"_postman_variable_scope": "environment",
	"_postman_exported_at": "2025-07-10T08:12:52.072Z",
	"_postman_exported_using": "Postman/11.50.1"
}
```
   

5. Set up GitHub environment (to run with GitHub actions).      
	a) add token and key to environment secrets. (Settings -> Environments -> Environment secrets)   
	b) add environment to .yml file. 

```
name: Node.js CI

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

jobs:
  build:

    runs-on: ubuntu-latest

    strategy:
      matrix:
        node-version: [18.x]

	environment: TrelloAPI

    steps:
    - uses: actions/checkout@v4
    - name: Use Node.js ${{ matrix.node-version }}
      uses: actions/setup-node@v4
      with:
        node-version: ${{ matrix.node-version }}
        cache: 'npm'
    - run: npm ci
    - run: npm run build --if-present
  
    - name: Install Newman
      run: npm install -g newman

    - name: Run Postman tests by package scripts
      env:
        TOKEN: ${{ secrets.TOKEN }}
        KEY: ${{secrets.KEY}}
      run: |
          newman run TrelloAPI.postman.json \
            --env-var "key=${{ secrets.KEY }}" \
            --env-var "token=${{ secrets.TOKEN }}"
```    

### 🧪 Running tests

```npm test```

### :book: Authors: 
Kristina Cv.

### 🔗 Other resources:   
No other resources.