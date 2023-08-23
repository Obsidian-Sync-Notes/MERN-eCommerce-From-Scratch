#backend 

So, now we will be modelling our data.

in `backend` folder create a folder named `models` [[Folder Structure]]
In this project we will need 3 models
1. userModel.js
2. productModel.js
3. orderModel.js

so, create all the files.

First lets create userModel, so first we will have to create userSchema

```js
import mongoose from 'mongoose'

const userSchema = mongoose.Schema({
	name:{
		type:String,
		required: true 
	},
	email:{
		type:String,
		required: true,
		unique:true
	},
	password:{
		type:String,
		required: true,
	},
	isAdmin:{
		type:Boolean,
		required:true,
		default:false
	}
},{
	timestamps:true
})

const User = mongoose.model('User', userSchema)

export default User

```

and add other fields as well. Do similar with other models as well.

```js
import mongoose from 'mongoose'

const reviewSchema = mongoose.Schema({
	name:{
		type:String,
		required:true
	},
	rating:{
		type:Number,
		required:true
	},
	comment:{
		type:String,
		required:true
	}, 
},{
	timestamps:true
})

const productSchema = mongoose.Schema({
	user:{
		type:mongoose.Schema.Types.ObjectId,
		required:true,
		ref:'User'
	},
	name:{
		type:String,
		required: true 
	},
	image:{
		type:String,
		required: true,
	},
	brand:{
		type:String,
		required: true,
	},
	category:{
		type:String,
		required:true,
	},
	description:{
		type:String,
		required:true,
	},
	reviews:[reviewSchema],
	rating:{
		type:Number,
		required:true,
		default:0
	},
	numReviews:{
		type:Number,
		required:true,
		default:0
	},
	price:{
		type:Number,
		required:true,
		default:0
	},
	countInStock:{
		type:Number,
		required:true,
		default:0
	}
},{
	timestamps:true
})

const Product = mongoose.model('Product', productSchema)

export default Product

```

Similarly make similar for orderModel.

```js
import mongoose from "mongoose";

const orderSchema = new mongoose.Schema({
  user: {
    type: mongoose.Schema.Types.ObjectId,
    required: true,
    ref: 'User'
  },
  orderItems: [{
    name: { type: String, required: true },
    qty: { type: Number, required: true },
    image: { type: String, required: true },
    price: { type: Number, required: true },
    product: {
      type: mongoose.Schema.Types.ObjectId,
      required: true,
      ref: 'Product'
    }
  }],
  shippingAddress: {
    address: { type: String, required: true },
    city: { type: String, required: true },
    postalCode: { type: String, required: true },
    country: { type: String, required: true },
  },
  paymentMethod: {
    type: String,
    required: true,
  },
  paymentResult: {
    id: { type: String },
    status: { type: String },
    update_time: { type: String },
    email_address: { type: String },
  },
  taxPrice: {
    type: Number,
    required: true,
    default: 0.0
  },
  shippingPrice: {
    type: Number,
    required: true,
    default: 0.0
  },
  totalPrice: {
    type: Number,
    required: true,
    default: 0.0
  },
  isPaid: {
    type: Boolean,
    required: true,
    default: false
  },
  paidAt: {
    type: Date
  },
  isDelivered: {
    type: Boolean,
    required: true,
    default: false
  },
  deliveredAt: {
    type: Date
  }
}, {
  timestamps: true
})

const Order = mongoose.model("Order", orderSchema)
export default Order
```

Next we will be preparing our [[16 Preparing Sample Data]]