#backend 

For this we have to install `dotenv` package in root.
```console
npm i dotenv
```


in `server.js` import doenv
```js
const dotenv =  require('dotenv')
```

 and just before initalising express
```js
dotenv.config()
```

Create a file `.env` in root.

```env
NODE_ENV = 'development'
PORT = 5000
```

Noe in the `server.js` use the port from `.env`
```js
const PORT = process.env.PORT || 5000

app.listen(PORT,console.log(
	`Server running in ${
	process.env.NODE_ENV
	} mode on port ${PORT}`
	)
)
```


Next we will be making imports in backend as ES6 syntax [[12 ES Modules in NodeJS]]