#backend 

Install  `jsonwebtoken` in the root.

For creating a token, we will write the logic in different file.
So create a folder `utils` inside `backend` folder.
In that create a file named `generateToken.js`

![[Pasted image 20230814034141.png]]

Now add the secret inside the `.env` file
![[Pasted image 20230814034229.png]]
We can also set expiry time
![[Pasted image 20230814034309.png]]

Now in `userController.js` import this `generateToken` function.

![[Pasted image 20230814034421.png]]

Now lets create [[36 Custom Authentication Middleware]]