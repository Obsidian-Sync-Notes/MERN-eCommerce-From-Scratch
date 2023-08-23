#backend 

Create a folder in the root called `backend`
[[Folder Structure]]
 `npm init` `root` folder for backend. We are not initialising backend folder we are initialising root folder.
```console
npm init
```

Entry point for our application will be `server.js`.

Install Express in the `root` 
```console
npm i express
```

Create a `server.js` file inside the `backend` folder. For now also copy paste the `products.js` file in data folder in backend.

```javascript
const express = require('express')

const app= express()

app.listen(5000, console.log('Server running on port 5000'))
```

So for running the `server.js` lets create a script in `package.json` 

addd this line in `package.json` 
```json
"script" : {
"start" : node backend/server.js
}
```

```javascript
app.get('/'. (req,res) =>{
	res.send('API is running .... }')
})
```

Change export of products from `product.js` to common module exports, currently it is in es6 module export.
```javascript
module.exports = products
```

```javascript
app.get('/api/products'. (req,res) =>{
	res.json(products)
})
```

Now we will create a route which will give a single product.

```javascript
app.get('/api/product/:id', (req,res) =>{
	const product = products.find(p=>p._id===req.params.id)
	res.json(products)
})
```

So this is an very basic server which will be serving product details.

We are using `nodemon` [[Nodemon]]

Here is the `sever.js` file.

```javascript

const express = require('express');
const products = require('./data/products');

const app = express();

app.listen(5000, console.log("Server is running on port 50000\n go to http://localhost:5000/"))

app.get('/', (req, res) => {
  res.send('API is running...');
})

app.get('/api/products', (req, res) => {
  res.json(products);
})

app.get('/api/product/:id', (req, res) => {
  const product = products.find(p => p._id === req.params.id)
  res.json(product)
})

```

Next step is [[09 Fetching Data in React]].