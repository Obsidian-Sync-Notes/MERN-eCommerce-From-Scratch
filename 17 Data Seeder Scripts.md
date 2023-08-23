#backend 

We will be creating seeder script so that we can easily import sample data.
Create a `seeder.js` in `backend` folder.

This is an independent file, so that we have to import everything separately.

make these imports
![[Pasted image 20230807233824.png]]


```js
dotenv.config()

  

connectDB()
```

Create these functions
 In import function, firstly we will be deleting all data from our database, then we will do a fresh import.
![[Pasted image 20230807234408.png]]
Here after clearing database, we are inserting users and also storing it in `createdUsers` variable and extracting its first user which is admin user and getting its `_id` which we can use in products data (so, that product will be inserted by admin user).

![[Pasted image 20230807234649.png]]

Function to destroy all the sample data
![[Pasted image 20230807234745.png]]

![[Pasted image 20230807235157.png]]

after this lets create a npm script for importing the data.

go into `package.json` in `root` and add these into scripts.
```json
"data:import": "node backend/seeder",
"data:destroy": "node backend/seeder -d"
```


now run the script `npm run data:import`
and check if data is inserted or not.


Also check after destroying data.


```js
import "colors"
import dotenv from "dotenv"
import users from "./data/users.js"
import products from "./data/products.js"
import User from "./models/userModel.js"
import Product from "./models/productModel.js"
import Order from "./models/orderModel.js"
import connectDB from "./config/db.js"

dotenv.config()

connectDB()


const importData = async () => {
  try {
    await Order.deleteMany()
    await Product.deleteMany()
    await User.deleteMany()

    const createdUsers = await User.insertMany(users)

    const adminUser = createdUsers[0]._id

    const sampleProducts = products.map(product => {
      return { ...product, user: adminUser }
    })

    await Product.insertMany(sampleProducts)

    console.log("Data Imported!".green.inverse)
    process.exit()
  } catch (error) {
    console.error(`${error}`.red.inverse)
    process.exit(1)
  }
}
const destroyData = async () => {
  try {
    await Order.deleteMany()
    await Product.deleteMany()
    await User.deleteMany()

    console.log("Data Destroyed!".red.inverse)
    process.exit()
  } catch (error) {
    console.error(`${error}`.red.inverse)
    process.exit(1)
  }
}

if (process.argv[2] === "-d") {
  destroyData()
} else {
  importData()
}

```

Next we will be fetching data from database and will be using them [[18 Fetching Products from Database]]
