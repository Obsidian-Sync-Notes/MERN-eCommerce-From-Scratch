#backend 

Now we will work on creating route

Lets create a request in postman first
![[Pasted image 20230815001327.png]]

Then in the `userController.js`

![[Pasted image 20230815001909.png]]
![[Pasted image 20230815002107.png]]

![[Pasted image 20230815002143.png]]

Then in `useRoutes.js`

![[Pasted image 20230815002252.png]]

Now we can check by making request, if we are not sending any data, then the error will come from mongoose.

Since we are not hashing the password, lets make a middleware to hash the password using bcryptjs.

![[Pasted image 20230815010358.png]]

Just this, we do not have to put it anywhere else, this piece of code will do all the work of hashing.


Next we will be creating [[39 User Login Reducer & Action]]