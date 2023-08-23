#backend 


For connecting our backend with database, we will be using mongoose.

In root install mongoose
```console
npm i mongoose
```

in backend create a folder called `config` [[Folder Structure]] and create a db.js

Create a function to establish a connection with database in `db.js` file.

```js
import mongoose from 'mongoose'

const connectDB = async()=>{
	try{
		const conn = await mongoose.connect(
			process.env.MONGO_URI,{
				useUnifiedTopology: true,
				useNewUrlParser: true,
				useCreateIndex: true,
			}
		)

		console.log(`MongoDB Connected :${
			conn.connection.host
			}`)
	} catch(error){
		console.error(`Error: ${error.message}`)
		process.exit(1)
	}
}

export default connectDB
```

import the function in `server.js` and call it before initiating express.

Now we will make our console beautiful (Optional) [[Adding Colors to Console (Optional)]].

Or, you can go here [[15 Modeling our data]]