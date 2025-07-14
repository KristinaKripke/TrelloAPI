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

4. Create TrelloEnv.postman.json file to add API-key and token

[Get Trello authorization here](https://developer.atlassian.com/cloud/trello/power-ups/rest-api-client/#client-initialization)

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

### 🧪 Running tests

```npm test```

### :book: Authors: 
Kristina Cv.

### 🔗 Other resources:   
No other resources.