#backend 

Lets prepare data to be imported into the database.

We will be using same `products.js` file for data, so lets remove `_id` field because, it will be automatically inserted while putting into database.


Lets also create user data, create a file `users.js` inside `data` folder [[Folder Structure]].

```js
const users = [
	{
		name: 'Admin User',
		email: 'admin@bunny.com',
		password: 'xxxxx',
		isAdmin: true,
	},{
		name: 'Roshan Gupta',
		email: 'roshan@bunny.com',
		password: 'xxxxx',
	},{
		name: 'Shreyas Lingareddy',
		email: 'shreyas@bunny.com',
		password: 'xxxxx',
	},
]
```

For storing passwords, we need to hash the password, for that we will be using `bcrypt`

```console
npm i bcryptjs
```

Import bcrypt
```js
import bcrypt from 'bcryptjs'
const users = [
	{
		name: 'Admin User',
		email: 'admin@bunny.com',
		password: bcrypt.hashSync('12345678',10),
		isAdmin: true,
	},{
		name: 'Roshan Gupta',
		email: 'roshan@bunny.com',
		password:bcrypt.hashSync('12345678',10),
	},{
		name: 'Shreyas Lingareddy',
		email: 'shreyas@bunny.com',
		password: bcrypt.hashSync('12345678',10),
	},
]

export default users
```

With this our sample data is ready, next we will be creating seeder scripts. [[17 Data Seeder Scripts]]