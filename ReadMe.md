# Trello API
![picture](/Blog-API.webp)
### API testing project

### 🌟 About
This project serves as an educational resource to test REST APIs using Postman, newman, and Node.js. It provides practical, hands-on experience with automating API tests, validating responses, and integrating tests into CI/CD workflows, running tests automatically with GitHub Actions.

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

```git i```

3. Install newman

```npm install newman```

4. Create TrelloEnv.postman.json file to add API-key and token

[Get Trello authorization here](https://developer.atlassian.com/cloud/trello/power-ups/rest-api-client/#client-initialization)

```
{
	"id": "6ac11d7c-b9a5-4a48-8b1f-4c6443d6369f",
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