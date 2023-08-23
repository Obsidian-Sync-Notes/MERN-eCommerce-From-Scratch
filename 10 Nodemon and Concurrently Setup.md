

Currently we have to manage both our frontend and backend server manually, so we will be using nodemon and concurrently to start frontend and backend server simultaneously.

Nodemon will be used for backend server [[Nodemon]].

In root folder install
```console
npm i -D nodemon concurrently
```
 `-D` flag will make these as dev dependencies.

Make changes to the script as 
```json
"scripts":{
	"start": "node backend/server",
	"server": "nodemon backend/server",
	"client": "npm start --prefix frontend",
	"dev": "concurrently \"npm run server\" \"npm run client\""
}
```


Next we will be setting up `.env` file for storing senstive information and port numbers etc. [[11 Environment Variables]]

